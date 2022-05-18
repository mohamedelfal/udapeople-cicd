
# [Prometheus Service Discovery on AWS EC2](./prometheus-on-aws-ec2-part3.md)
Author: [Héctor Rosales](https://codewizardly.com/authors/hector/)
![image](https://user-images.githubusercontent.com/100445644/168937235-8241dfaf-92fe-4d80-9334-175c16c1a034.png)
   
Follow the complete story:

[1- Install Prometheus on AWS EC2](./prometheus-on-aws-ec2-part1.md)  
[2- Prometheus Node Exporter on AWS EC2](./prometheus-on-aws-ec2-part2.md)  
[3- Prometheus Discovery Service on AWS EC2](./prometheus-on-aws-ec2-part3.md)  
[4- Prometheus Alertmanager Sending Emails](./prometheus-on-aws-ec2-part4.md)  

Cool, now you have Prometheus and Node Exporter up and running.   
What if you want to add a third EC2 instance? A trivial task, you only need to go back to Prometheus, update its static configuration and restart the service, manually.   
So, every time some change is needed, you might need to do it yourself or hire Bob if your name is Bob, don’t take it personal.   
to work on that on the weekends. Also, consider human errors, the stack of another tasks we hide behind the Kanban board, and the fact that we all are a little bit lazy.   
I think I have made my point, we need to automate this process. Don’t worry, Prometheus got our backs, now meet Prometheus Service Discovery feature.

Well, in fact, there are many service discovery options out there.   
Check out the [list](https://github.com/prometheus/prometheus/tree/master/discovery).   
In our case we are going to use EC2 Service Discovery.

**Create an IAM User**   
This part might be confusing if you are not familiar with AWS IAM just because the new terms behind what is needed. Let’s talk about a few concepts first:

**User**  
 >“An AWS Identity and Access Management (IAM) user is an entity that you create in AWS to represent the person or application that uses it to interact with AWS. A user in AWS consists of a name and credentials.” Read more

**Policy**  
 >“A policy is an object in AWS that, when associated with an identity or resource, defines their permissions. IAM policies define permissions for an action regardless of the method that you use to perform the operation.” Read more

**Instructions**  
First, select **IAM** from the AWS Services using the search bar.

![Select IAM](https://user-images.githubusercontent.com/100445644/168937861-b7b77b9f-7b8b-4666-9daf-6cfa76894ffd.png)  

Select **Users** from the sidebar menu.

![Select User](https://user-images.githubusercontent.com/100445644/168938142-0b9d842b-7e3d-4237-bb39-094133d55873.png)  
  
Click on **Add user** button.   

![Add User](https://user-images.githubusercontent.com/100445644/168938190-f7ceb797-9088-451f-a6e7-afe3ad6c2059.png)  

Set user details Pick a name of your preference for the new user and fill the blank space.   
Also, give the user just **Programmatic access**, our user will not login to AWS Console which is the user interface we are currently using.

![Set User Details](https://user-images.githubusercontent.com/100445644/168938498-5e7f19e9-bfee-454a-ae98-5dcff0407aaf.png)  

Set permissions for the new user. At this point, the new user is not capable to do nothing.   
Attach an existing policy using the filter and looking for **`AmazonEC2ReadOnlyAccess`**.
 >“IAM enables security best practices by allowing you to grant unique security credentials to users and groups to specify which AWS service APIs and resources they can access. IAM is secure by default; users have no access to AWS resources until permissions are explicitly granted.”

![Set Permissions](https://user-images.githubusercontent.com/100445644/168938650-44d348be-53d5-4a2d-abad-ab982fa0f1e6.png)  

Add tags. This step is optional but it is a good idea to add tags for future reference.   
The number of IAM users often grows without any control and without a reference is really hard to tell which user you actually need.   
Remember that every user means a potential target for attackers and it could be an open door to your AWS account.

![UserTags](https://user-images.githubusercontent.com/100445644/168938769-96943212-0fb4-4f2f-8f88-8e7215b13fab.png)  

Review the details of the new user.


![Review User](https://user-images.githubusercontent.com/100445644/168938826-4256f88b-2208-4f24-9ec2-24eae8f36b98.png)  


Save the credentials in a safe place.   
It is really important to keep these values in a safe place.   
With these credentials anyone could use your AWS account and generate bills.  

![Save Credentials](https://user-images.githubusercontent.com/100445644/168938904-e720ec9b-06ab-4bf4-8efe-2cbbad40789f.png)  

## Configure Prometheus Service Discovery
Now we need to go back to Prometheus and change the configuration again.   
Remember that `ec2-3-17-28.53.us-east-2.compute.amazonaws.com` is the DNS value I got from my configuration and yours should be something different.

Start a session in the Prometheus host virtual machine.

```console
ssh -i prometheus.pem ubuntu@ec2-3-17-28.53.us-east-2.compute.amazonaws.com
``` 

Edit `/etc/prometheus/prometheus.yml` file.   
Notice the `region` property, this could be different in your setup.

```yml
global:
  scrape_interval: 1s
  evaluation_interval: 1s

scrape_configs:
  - job_name: 'node'
    ec2_sd_configs:
      - region: us-east-1
        access_key: PUT_THE_ACCESS_KEY_HERE
        secret_key: PUT_THE_SECRET_KEY_HERE
        port: 9100
        
```
Restart Prometheus service.

```bash
sudo systemctl restart prometheus
```

**Try It Out**   
Let’s see if Prometheus is finding our Node-Exporter instance.   
Go to ***`http://ec2-3-17-28.53.us-east-2.compute.amazonaws.com:9090/targets`***.   
You might see other instances registered since Prometheus is looking up for all the EC2 instances in the same network.Service Discovery
