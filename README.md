
# Udacity Advanced Cloud DevOps 

### Give your Application Auto-Deploy Superpowers
Project *№3*: **Udapeople**   
*Cloud DevOps Project*
## Table Of Contents
* [Udapeople](#udapeople)
* [Prerequisites](#prerequisites)
* [Built With](#built-with)
* [Section 1](#section-1)
* [Section:1 file](#section-1-file)
* [Section 2](#section-2)
* [Section:2 files](#section-2-files)
* [Files Included](#files-included)
* [License](#license)

# Udapeople 
A CI-CD pipeline for a client/server TypeScript project hosted on AWS EC2 and CloudFront and monitored with Prometheus, with Slack and E-mail notifications used for alerts.

## Prerequisites
* [`Nodejs 13`](https://nodejs.org/en/)
* [`Docker`](https://www.docker.com/)
* [`GitHub account`](https://github.com/)
* [`CircleCi account`](https://circleci.com/)
* [`AWS account`](https://aws.amazon.com/)
* [`ThisDB api key and bucket`](https://thisdb.com/)

## Built With

- [`Circle CI`](www.circleci.com) - Cloud-based CI/CD service
- [`Amazon AWS`](https://aws.amazon.com/) - Cloud services
- [`AWS CLI`](https://aws.amazon.com/cli/) - Command-line tool for AWS
- [`CloudFormation`](https://aws.amazon.com/cloudformation/) - Infrastrcuture as code
- [`Ansible`](https://www.ansible.com/) - Configuration management tool
- [`Prometheus`](https://prometheus.io/) - Monitoring tool

# Section 1: 
## Selling CI/CD to your Team/Organization
Explain the Fundamentals and Benefits of CI/CD to Achieve, Build, and Deploy Automation for Cloud-Based Software Products
>The CI/CD benefits proposal contains essential benefits of CI/CD, and describes the business context that will benefit from the automation tools.  
>Explanation should include benefits that translate to revenue and cost for the business.
* **focus on** benefits that **create revenue, protect revenue, control costs**, or **reduce costs**.
* The deliverable should be "near-production-quality", but you should try to time-box your work to about 30 minutes.
  >*Your presentation should be no longer than 5 slides*
* Your presentation should be in `PDF` format named [`"presentation.pdf"`](./presentation.pdf) and should be included in your code repository root folder
## Section 1: file
* [`"presentation.pdf"`](./presentation.pdf)

# Section 2: 
## Deploying Working, Trustworthy Software
Utilize Deployment Strategies to design and build CI/CD pipelines that support Continuous Delivery processes.

* A public git repository with your project code. [URL01](https://github.com/mohamedelfal/udapeople-cicd)
  * `url`: https://github.com/mohamedelfal/udapeople-cicd

* Evidence of code-based CI/CD configuration in the form of `yaml` files in your git repository.
  * [`yaml` file](./.circleci/config.yaml)
Console output of various pre-deploy job failure scenarios:

Build Jobs that failed because of compile errors. [SCREENSHOT01](./screenshots/SCREENSHOT01.png)  
Failed unit tests. [SCREENSHOT02](./screenshots/SCREENSHOT02.png)  
Failure because of vulnerable packages. [SCREENSHOT03](./screenshots/SCREENSHOT03.png)  
An alert from one of your failed builds. [SCREENSHOT04](./screenshots/)  
Evidence in your code that:  

Compile errors have been fixed.  
Unit tests have been fixed.  
All critical security vulnerabilities caught by the “Analyze” job have been fixed.  

## Section 2: Files
* A public git repository with your project code. [URL01](https://github.com/mohamedelfal/udapeople-cicd)
  * [`url.txt`](./url.txt) - File containing a public git repository url : https://github.com/mohamedelfal/udapeople-cicd
* [`config.yaml`]((./.circleci/config.yaml)) - code-based CI/CD configuration in the form of `yaml` files in git repository.
  * [`config.yaml`](./.circleci/config.yaml)
* [Screenshots folder](./screenshots/) - This folder contains all required screenshots
  * [SCREENSHOT01](./screenshots/SCREENSHOT01.png)

  * [SCREENSHOT02](./screenshots/SCREENSHOT02.png)

  * [SCREENSHOT03](./screenshots/SCREENSHOT03.png)

  * [SCREENSHOT04](./screenshots/)

  * [and more..](./screenshots/)

## Files Included
* [`.circleci` folder](./.circleci)
* [`backend` folder](./backend)
* [`frontend` folder](./frontend)
* [`util` folder](./util)
* [`.gitignore` folder](./.gitignore)
* [`Screenshots` folder](./screenshots/)
* [`"presentation.pdf"` file](./presentation.pdf)
* [`url.txt` file](./url.txt)
* [`README.md` file](./README.md)
* [`LICENSE.md` file](./LICENSE.md)

## License
* [**License**](./LICENSE.md)
