

<h1 align="lift">Udacity Advanced Cloud DevOps</h1>  

[![CircleCI](https://circleci.com/gh/mohamedelfal/udapeople-cicd/tree/master.svg?style=shield)](https://circleci.com/gh/mohamedelfal/udapeople-cicd/tree/master)
[![GitHub license](https://img.shields.io/badge/license-Udacity-blue.svg)](./LICENSE.md)
<a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-nd/4.0/80x15.png" /></a><br /><a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/"></a>
 
    

<!-- Adding Status Badges circleci Template
# Template:
[![<ORG_NAME>](https://circleci.com/<VCS>/<ORG_NAME>/<PROJECT_NAME>.svg?style=svg)](<LINK>)

# Example:
[![CircleCI](https://circleci.com/gh/Mohamedelfal/udapeople-cicd.svg?style=svg)](https://app.circleci.com/pipelines/github/mohamedelfal/udapeople-cicd/5)

# Example for specific branch:
[![CircleCI](https://circleci.com/gh/circleci/circleci-docs/tree/teesloane-patch-5.svg?style=svg)](https://circleci.com/gh/circleci/circleci-docs/?branch=teesloane-patch-5)
<PROJECT_NAME> - Your project’s name. Example: circleci-docs
<ORG_NAME> - The organization or user name the project in question belongs to
<VCS> - your VCS provider (gh for “github” and bb for BitBucket)
<LINK> - The link you want the status badge to go to when clicked (example: the pipeline overview page)
Optional: an API token (to create badges for private projects)
-->

<h2 align="center">Build CI/CD Pipelines, Monitoring & Logging</h2>  
<h3 align="center">Give Your Application Auto-Deploy Superpowers</h3>   
<h4 align="center">UdaPeople<i>(Cloud-Based Software)</i></h4>  
    
## Table Of Contents
* [Udapeople](#udapeople)
* [Prerequisites](#prerequisites)
* [Built With](#built-with)
* [Section 1: Selling CI/CD to your Team/Organization](#section-1-selling-cicd-to-your-teamorganization)
* [ection 2: Deploying Working, Trustworthy Software](#section-2-deploying-working-trustworthy-software)
* [Section 3: Turn Errors into Sirens](#section-3-turn-errors-into-sirens)
* [Files Included](#files-included)
* [License](#license)

<h3 align="center">UdaPeople</h3>   

<p align="center">
  <img width="" height="" src="./udapeople.png">
</p>
<p align="center">
  A CI-CD pipeline for a client/server TypeScript project 
hosted on AWS EC2 and CloudFront and monitored with Prometheus,<br>
with Slack and E-mail notifications used for alerts.<br>"<small><i>the fictional "UdaPeople" Product is  (Cloud-Based Software) Product,  a revolutionary concept in Human Resources which promises to help small businesses care better for their most valuable resource: their people."</i></small>
</p>


<h3 align="center">UdaPeople Pipeline</h3>   

<p align="center">
  <img width="" height="" src="./udapeople-pipeline.png"  
</p>

## Prerequisites
* [Nodejs 13](https://nodejs.org/en/)
* [Docker](https://www.docker.com/)
* [GitHub account](https://github.com/)
* [CircleCi account](https://circleci.com/)
* [AWS account](https://aws.amazon.com/)
* [kvdb api bucket](https://kvdb.io/)
* [Slack api App](https://api.slack.com/)

## Built With

- [Circle CI](www.circleci.com) - Cloud-based CI/CD service
- [Amazon AWS](https://aws.amazon.com/) - Cloud services
- [AWS CLI](https://aws.amazon.com/cli/) - Command-line tool for AWS
- [CloudFormation](https://aws.amazon.com/cloudformation/) - Infrastrcuture as code
- [Ansible](https://www.ansible.com/) - Configuration management tool
- [Prometheus](https://prometheus.io/) - Monitoring tool
#
<h2 align="center">Project Submission</h2>  

<p align="center">
  <img width="" height="" src="./pipeline.jpg"  
</p>
    

<h3 align="center">Section 1: Selling CI/CD to your Team/Organization</h3>  


|CRITERIA|MEETS SPECIFICATIONS |Files |Status|
|:-----|:-----|:-----|:-----|
|Explain the fundamentals and benefits of CI/CD to achieve, build, and deploy automation for cloud-based software products.|The CI/CD benefits proposal contains essential benefits of CI/CD, and describes the business context that will benefit from the automation tools. Explanation should include benefits that translate to revenue and cost for the business.|[presentation.pdf](./presentation.pdf)|[![presentation.pdf1](https://img.shields.io/badge/PDF-EXISTS-brightgre)](./presentation.pdf)  |


<h3 align="center">Section 2: Deploying Working, Trustworthy Software</h3>  


|CRITERIA|MEETS SPECIFICATIONS |Files |Status|
|:-----|:-----|:-----|:-----|
|Utilize Deployment Strategies to design and build CI/CD pipelines that support Continuous Delivery processes.|A public git repository with your project code. |[URL01](https://github.com/mohamedelfal/udapeople-cicd/)<br>https://github.com/mohamedelfal/udapeople-cicd/|[![url1](https://img.shields.io/badge/URL01-EXISTS-brightgre)](https://github.com/mohamedelfal/udapeople-cicd/) |
||Evidence of code-based CI/CD configuration in the form of yaml files in your git repository.|[config.yml](./.circleci/config.yml)|[![config.yml](https://img.shields.io/badge/config.yml-EXISTS-brightgre)](./.circleci/config.yml) <br> [![CircleCI](https://circleci.com/gh/mohamedelfal/udapeople-cicd/tree/main.svg?style=shield)](https://circleci.com/gh/mohamedelfal/udapeople-cicd/tree/main)  |
||***Console output of various pre-deploy job failure scenarios:***||
||Build Jobs that failed because of compile errors. |[SCREENSHOT01](./screenshots/SCREENSHOT01.jpg)|[![SCREENSHOT01](https://img.shields.io/badge/SCREENSHOT01-EXISTS-brightgre)](./screenshots/SCREENSHOT01.jpg) <br> |
||Failed unit tests. |[SCREENSHOT02](./screenshots/SCREENSHOT02.jpg)|[![SCREENSHOT02](https://img.shields.io/badge/SCREENSHOT02-EXISTS-brightgre)](./screenshots/SCREENSHOT02.jpg) <br> |
||Failure because of vulnerable packages. |[SCREENSHOT03](./screenshots/SCREENSHOT03.jpg)|[![SCREENSHOT03](https://img.shields.io/badge/SCREENSHOT03-EXISTS-brightgre)](./screenshots/SCREENSHOT03.jpg) <br>|
||An alert from one of your failed builds. |[SCREENSHOT04](./screenshots/SCREENSHOT04.png) e-mail Notification<br>[SCREENSHOT04](./screenshots/SCREENSHOT04.jpg) slack Notification |[![SCREENSHOT04](https://img.shields.io/badge/E_mail_Alert-PASSED-brightgre)](./screenshots/SCREENSHOT04.png) <br> [![SCREENSHOT04](https://img.shields.io/badge/Slack_Alert-PASSED-brightgre)](./screenshots/SCREENSHOT04.jpg)|
||***Evidence in your code that:*** Compile errors have been fixed.<br>Unit tests have been fixed.<br>All critical security vulnerabilities caught by the “Analyze” job have been fixed|[.circleci](./.circleci)<br>[backend](./backend)<br>[frontend](./frontend)|[![CircleCI](https://circleci.com/gh/mohamedelfal/udapeople-cicd/tree/main.svg?style=shield)](https://circleci.com/gh/mohamedelfal/udapeople-cicd/tree/main)|
|Utilize a configuration management tool to accomplish deployment to cloud-based servers.|Console output of appropriate failure for infrastructure creation job (using CloudFormation). |[SCREENSHOT05](./screenshots/SCREENSHOT05.jpg)|[![SCREENSHOT05](https://img.shields.io/badge/SCREENSHOT05-EXISTS-brightgre)](./screenshots/SCREENSHOT05.jpg) <br>|
||Console output of a smoke test job that is failing appropriately. |[SCREENSHOT06](./screenshots/SCREENSHOT06.jpg)|[![SCREENSHOT06](https://img.shields.io/badge/SCREENSHOT06-EXISTS-brightgre)](./screenshots/SCREENSHOT06.jpg) <br>|
||Console output of a successful rollback after a failed smoke test. |[SCREENSHOT07](./screenshots/SCREENSHOT07.jpg)|[![SCREENSHOT07](https://img.shields.io/badge/SCREENSHOT07-EXISTS-brightgre)](./screenshots/SCREENSHOT07.jpg) <br>|
||Console output of successful promotion of new version to production in CloudFront. |[SCREENSHOT08](./screenshots/SCREENSHOT08.jpg)|[![SCREENSHOT08](https://img.shields.io/badge/SCREENSHOT08-EXISTS-brightgre)](./screenshots/SCREENSHOT08.jpg) <br>|
||Console output of successful cleanup job that removes old S3 bucket and EC2 instance. |[SCREENSHOT09](./screenshots/SCREENSHOT09.jpg)|[![SCREENSHOT09](https://img.shields.io/badge/SCREENSHOT09-EXISTS-brightgre)](./screenshots/SCREENSHOT09.jpg) <br>|
||Evidence that the deploy jobs only happen on the master branch. |[SCREENSHOT10](./screenshots/SCREENSHOT10.jpg)|[![SCREENSHOT10](https://img.shields.io/badge/SCREENSHOT10-EXISTS-brightgre)](./screenshots/SCREENSHOT10.jpg) <br>|
||Evidence of deployed and functioning front-end application in an S3 bucket .|[URL02]<br>[URL02_SCREENSHOT](./screenshots/URL02_SCREENSHOT.jpg)|[![URL02](https://img.shields.io/badge/URL02-EXISTS-brightgre)](./screenshots/screenshots/URL02_SCREENSHOT.jpg) <br>|
||Evidence of deployed and functioning front-end application in CloudFront. |[URL03_SCREENSHOT](./screenshots/URL03_SCREENSHOT.jpg)|[![URL03](https://img.shields.io/badge/URL03-EXISTS-brightgre)](./screenshots/screenshots/URL03_SCREENSHOT.jpg) <br>|
||Evidence of healthy back-end application. |[URL02]<br>[URL04_SCREENSHOT](./screenshots/URL04_SCREENSHOT.jpg)|[![URL04](https://img.shields.io/badge/URL04-EXISTS-brightgre)](./screenshots/URL04_SCREENSHOT.jpg) <br>|

<h3 align="center">Section 3: Turn Errors into Sirens</h3>  

|CRITERIA|MEETS SPECIFICATIONS |Files |Status|
|:-----|:-----|:-----|:-----|
|Surface critical server errors for diagnosis using centralized logging.|Evidence of Prometheus Server. |[URL05]<br>[URL05_SCREENSHOT](./screenshots/URL05_SCREENSHOT.jpg)|[![URL05](https://img.shields.io/badge/URL05-EXISTS-brightgre)](./screenshots/screenshots/URL05_SCREENSHOT.jpg) <br>|
||Evidence that Prometheus is monitoring memory, cpu and disk usage of EC2 instances. |[SCREENSHOT11](./screenshots/SCREENSHOT11.jpg)|[![SCREENSHOT11](https://img.shields.io/badge/SCREENSHOT11-EXISTS-brightgre)](./screenshots/SCREENSHOT11.jpg) <br>|
||Evidence that Prometheus and AlertManager send alerts when certain conditions exist in the EC2 instance. |[SCREENSHOT12](./screenshots/SCREENSHOT12.jpg)|[![SCREENSHOT12](https://img.shields.io/badge/SCREENSHOT12-EXISTS-brightgre)](./screenshots/SCREENSHOT12.jpg) <br>|

## Files Included
* [.circleci](./.circleci)  
* [backend](./backend)
* [frontend](./frontend)  
* [util](./util)  
* [.gitignore](./.gitignore)  
* [Screenshots](./screenshots/)  
* [presentation.pdf](./presentation.pdf)  
* [urls.txt](./urls.txt)    
* [README.md](./README.md)  
* [LICENSE.md](./LICENSE.md)  

## License  
[![GitHub license](https://img.shields.io/badge/license-Udacity-blue.svg)](./LICENSE.md)   <a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-nd/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/">Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License</a>

<!-- small <a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-nd/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/">Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License</a>. -->

<!--- big <a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-nd/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/">Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License</a>. -->
