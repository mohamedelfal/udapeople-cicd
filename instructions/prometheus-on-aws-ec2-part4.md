

# [4- Prometheus Alertmanager Sending Emails](./prometheus-on-aws-ec2-part4.md)  
Author: [Héctor Rosales](https://codewizardly.com/authors/hector/)  

![Featured image](https://user-images.githubusercontent.com/100445644/168940308-ad1a2f69-4e76-4b99-bea7-a49c95f93740.png)

Let’s recap, we have a Prometheus instance on an AWS EC2 instance configured to discover services on port `9100` in the same network and one Node Exporter instance collecting OS metrics that can be easily upgraded to many Node Exporter instances as desired.

Follow the whole history:   
[1- Install Prometheus on AWS EC2](./prometheus-on-aws-ec2-part1.md)  
[2- Prometheus Node Exporter on AWS EC2](./prometheus-on-aws-ec2-part2.md)  
[3- Prometheus Discovery Service on AWS EC2](./prometheus-on-aws-ec2-part3.md)  
[4- Prometheus Alertmanager Sending Emails](./prometheus-on-aws-ec2-part4.md)  

But we are not done yet, we don’t want to be monitoring by ourselves.   
Prometheus can send us an alert to an email when it finds something.   
Let’s configure some rules and Prometheus Alertmanager with a Gmail account to accomplish this.

 >“The Alertmanager handles alerts sent by client applications such as the Prometheus server. It takes care of deduplicating, grouping, and routing them to the correct receiver integrations such as email, PagerDuty, or OpsGenie. It also takes care of silencing and inhibition of alerts.” [Read more](https://github.com/prometheus/alertmanager).

**Install Alertmanager**   
Login in the Prometheus instance.  
Don’t forget to replace this line with your configuration.

```bash
ssh -i prometheus.pem ubuntu@ec2-3-17-28.53.us-east-2.compute.amazonaws.com
```

Install Alertmanager.  

```bash
wget https://github.com/prometheus/alertmanager/releases/download/v0.21.0/alertmanager-0.21.0.linux-amd64.tar.gz
tar xvfz alertmanager-0.21.0.linux-amd64.tar.gz

sudo cp alertmanager-0.21.0.linux-amd64/alertmanager /usr/local/bin
sudo cp alertmanager-0.21.0.linux-amd64/amtool /usr/local/bin/
sudo mkdir /var/lib/alertmanager

rm -rf alertmanager*

```
Add Alertmanager’s configuration `/etc/prometheus/alertmanager.yml`.

```yml
route:
  group_by: [Alertname]
  receiver: email-me

receivers:
- name: email-me
  email_configs:
  - to: EMAIL_YO_WANT_TO_SEND_EMAILS_TO
    from: YOUR_EMAIL_ADDRESS
    smarthost: smtp.gmail.com:587
    auth_username: YOUR_EMAIL_ADDRESS
    auth_identity: YOUR_EMAIL_ADDRESS
    auth_password: YOUR_EMAIL_PASSWORD
    
```

Configure Alertmanager as a service. `/etc/systemd/system/alertmanager.service`

```service
[Unit]
Description=Alert Manager
Wants=network-online.target
After=network-online.target

[Service]
Type=simple
User=prometheus
Group=prometheus
ExecStart=/usr/local/bin/alertmanager \
  --config.file=/etc/prometheus/alertmanager.yml \
  --storage.path=/var/lib/alertmanager

Restart=always

[Install]
WantedBy=multi-user.target

```  

Configure Systemd   
```bash
sudo systemctl daemon-reload
sudo systemctl enable alertmanager
sudo systemctl start alertmanager
```

**Generate an App Password**   
You could use an App password if you don’t feel comfortable writing your e-mail’s password in plain text or if you have 2FA enabled.

 >An App Password is a 16-digit passcode that gives a non-Google app or device permission to access your Google Account. App Passwords can only be used with accounts that have 2-Step Verification turned on.

Go to your account: https://myaccount.google.com

From the left menu select **Security**

![Security](https://user-images.githubusercontent.com/100445644/168941111-296d6fbf-f136-49e4-bfbc-045b00effb55.png)  

Select the Signing in to Google panel select **App Passwords**.  
For this step it is also required the following:

1- 2fa Verification is set up for your account.  
2- 2fa Verification is not set up for security keys only.  
3- Your account is not through work, school, or other organization.  
4- You’ve not turned on Advanced Protection for your account.   

![app-passwords](https://user-images.githubusercontent.com/100445644/168941615-3871898f-32b4-421f-8775-e879ef47d229.png)

Create a new App password.  

![image](https://user-images.githubusercontent.com/100445644/168941392-ca408371-8b3d-42fc-b0a5-8ccd37ac9399.png)


Choose a custom name for the App password.  

![Custom Name](https://user-images.githubusercontent.com/100445644/168943094-c05213ea-9609-422d-84ad-edae93d6459a.png)

Save the App password in a safe place.    
  
![Save Credentials](https://user-images.githubusercontent.com/100445644/168941856-e16e0dfe-562a-4473-997e-58a89ee6b032.png)

**Create a Rule**  
This is just a simple alert rule.   
In a nutshell it alerts when an instance has been down for more than 3 minutes.   
Add this file at `/etc/prometheus/rules.yml`.

```yml
groups:
- name: Down
  rules:
  - alert: InstanceDown
    expr: up == 0
    for: 3m
    labels:
      severity: 'critical'
    annotations:
      summary: "Instance  is down"
      description: " of job  has been down for more than 3 minutes."
      
```

**Configure Prometheus**  
Let’s change the permissions of the directories, files and binaries we just added to our system.

```bash
sudo chown -R prometheus:prometheus /etc/prometheus
```

Update Prometheus configuration file. Edit `/etc/prometheus/prometheus.yml`.

```yml
global:
  scrape_interval: 1s
  evaluation_interval: 1s

rule_files:
 - /etc/prometheus/rules.yml

alerting:
  alertmanagers:
  - static_configs:
    - targets:
      - localhost:9093

scrape_configs:
  - job_name: 'node'
    ec2_sd_configs:
      - region: us-east-1
        access_key: PUT_THE_ACCESS_KEY_HERE
        secret_key: PUT_THE_SECRET_KEY_HERE
        port: 9100
        
```  

Reload Systemd

```bash
sudo systemctl restart prometheus
```

**Try It Out**  
Turn off the Node Exporter AWS EC2 Instance   

![Stop EC2 Instance](https://user-images.githubusercontent.com/100445644/168942411-c2d090a7-9564-40ac-8100-8f503c0fb16c.png)  

Wait for 3 minutes and check the Alertmanager URL that is installed in your `prometheus-server` instance:   
`http://ec2-34-229-224-133.compute-1.amazonaws.com:9093/#/alerts`   
As always, remember that you need to use a different URL depending on your AWS EC2 instance details.  


**Check your email**   
![Alert Email](https://user-images.githubusercontent.com/100445644/168942573-d649d5ca-a9e0-4990-be0f-75af89afe5c8.png)


