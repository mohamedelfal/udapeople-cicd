
# Udacity Advanced Cloud DevOps 

### Give your Application Auto-Deploy Superpowers
Project *№3*: **Udapeople**   
*Cloud DevOps Project*
## Table Of Contents
* [Udapeople](#udapeople)
* [Prerequisites](#prerequisites)
* [Built With](#built-with)
* [Files Included](#files-included)
* [License](#license)
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

A public git repository with your project code. [URL01](https://github.com/mohamedelfal/udapeople-cicd)

Evidence of code-based CI/CD configuration in the form of `yaml` files in your git repository.

Console output of various pre-deploy job failure scenarios:

Build Jobs that failed because of compile errors. [SCREENSHOT01](./screenshots/SCREENSHOT01.png)
Failed unit tests. [SCREENSHOT02](./screenshots/SCREENSHOT02.png)
Failure because of vulnerable packages. [SCREENSHOT03](./screenshots/SCREENSHOT03.png)
An alert from one of your failed builds. [SCREENSHOT04])(./screenshots/)
Evidence in your code that:

Compile errors have been fixed.
Unit tests have been fixed.
All critical security vulnerabilities caught by the “Analyze” job have been fixed.


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

## Files Included
* [`.circleci`](./.circleci)
* [`backend`](./backend)
* [`frontend`](./frontend)
* [`util`](./util)
* [`README.md`](./README.md)
* [`.gitignore`](./.gitignore)
* [`LICENSE.md`](./LICENSE.md)

## License
* [**License**](./LICENSE.md)
