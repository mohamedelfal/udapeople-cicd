
# Udacity Advanced Cloud DevOps 

### Give your Application Auto-Deploy Superpowers
Project *№3*: **Udapeople**   
*Cloud DevOps Project*
## Table Of Contents
* [Udapeople](#udapeople)
* [Prerequisites](#prerequisites)
* [Built With](#built-with)
* [Section 1](#section-1)
* [Section: 1 file](#section-1-file)
* [Section 2](#section-2)
* [Section: 2 files](#section-2-files)
* [Section 3](#section-3)
* [Section: 3 files](#section-3-files)
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

# Section 1
## Selling CI/CD to your Team/Organization
Explain the Fundamentals and Benefits of CI/CD to Achieve, Build, and Deploy Automation for Cloud-Based Software Products
>The CI/CD benefits proposal contains essential benefits of CI/CD, and describes the business context that will benefit from the automation tools.  
>Explanation should include benefits that translate to revenue and cost for the business.
* **focus on** benefits that **create revenue, protect revenue, control costs**, or **reduce costs**.
* The deliverable should be "near-production-quality", but you should try to time-box your work to about 30 minutes.
  >*Your presentation should be no longer than 5 slides*
* Your presentation should be in `PDF` format named ["presentation.pdf"](./presentation.pdf) and should be included in your code repository root folder
## Section 1: file
* [`presentation.pdf`](./presentation.pdf)

# Section 2
## Deploying Working, Trustworthy Software
## Utilize Deployment Strategies to design and build CI/CD pipelines that support Continuous Delivery processes.
Utilize Deployment Strategies to design and build CI/CD pipelines that support Continuous Delivery processes.

* A public git repository with your project code. [URL01]
* Evidence of code-based CI/CD configuration in the form of yaml files in your git repository.

Console output of various pre-deploy job failure scenarios:
* Build Jobs that failed because of compile errors. [SCREENSHOT01]
* Failed unit tests. [SCREENSHOT02]
* Failure because of vulnerable packages. [SCREENSHOT03]
* An alert from one of your failed builds. [SCREENSHOT04]
* Evidence in your code that:  
  * Compile errors have been fixed.  
  * Unit tests have been fixed.  
  * All critical security vulnerabilities caught by the “Analyze” job have been fixed.  

## Utilize a configuration management tool to accomplish deployment to cloud-based servers.
* Console output of appropriate failure for infrastructure creation job (using CloudFormation). [SCREENSHOT05]

* Console output of a smoke test job that is failing appropriately. [SCREENSHOT06]

* Console output of a successful rollback after a failed smoke test. [SCREENSHOT07]

* Console output of successful promotion of new version to production in CloudFront. [SCREENSHOT08]

* Console output of successful cleanup job that removes old S3 bucket and EC2 instance. [SCREENSHOT09]

* Evidence that deploy jobs only happen on master branch. [SCREENSHOT10]

* Evidence of deployed and functioning front-end application in an S3 bucket [URL02] and in CloudFront. [URL03]

* Evidence of healthy back-end application. [URL04]


## Section 2: Files
## Utilize Deployment Strategies to design and build CI/CD pipelines that support Continuous Delivery processes.
* A public git repository with your project code. [URL01](https://github.com/mohamedelfal/udapeople-cicd)
  * [`URL01.txt`](./URL01.txt) - File containing a public git repository [`url`](https://github.com/mohamedelfal/udapeople-cicd) : https://github.com/mohamedelfal/udapeople-cicd <br> <br>
* [`config.yml`]((./.circleci/config.yml)) - code-based CI/CD configuration in the form of `yaml` files in git repository.
  * [`config.yml`](./.circleci/config.yml) <br> <br>
* [`Screenshots folder](./screenshots/) - This folder contains all required screenshots:
  * Build Jobs that failed because of compile errors.
  * Failed unit tests.  
  * Failure because of vulnerable packages.
  * An alert from one of your failed builds. 
  * Evidence in your code that:  
     * Compile errors have been fixed.  
     * Unit tests have been fixed.  
     * All critical security vulnerabilities caught by the “Analyze” job have been fixed.  

## Utilize a configuration management tool to accomplish deployment to cloud-based servers.
* Console output of appropriate failure for infrastructure creation job (using CloudFormation). [SCREENSHOT05]
  * [SCREENSHOT05](./screenshots/)
* Console output of a smoke test job that is failing appropriately. [SCREENSHOT06]
  * [SCREENSHOT06](./screenshots/)
* Console output of a successful rollback after a failed smoke test. [SCREENSHOT07]
  * [SCREENSHOT07](./screenshots/)
* Console output of successful promotion of new version to production in CloudFront. [SCREENSHOT08]
  * [SCREENSHOT08](./screenshots/)
* Console output of successful cleanup job that removes old S3 bucket and EC2 instance. [SCREENSHOT09]
  * [SCREENSHOT09](./screenshots/)
* Evidence that deploy jobs only happen on master branch. [SCREENSHOT10]
  * [SCREENSHOT10](./screenshots/)
* Evidence of deployed and functioning front-end application in an S3 bucket [URL02] and in CloudFront. [URL03]
  * [URL02](./URL02.txt)
  * [URL03](./URL03.txt)
* Evidence of healthy back-end application. [URL04]
  * [URL04](./URL04.txt)

# Section 3
## Turn Errors into Sirens
## Surface critical server errors for diagnosis using centralized logging.
* Evidence of Prometheus Server. [URL05]
* Evidence that Prometheus is monitoring memory, cpu and disk usage of EC2 instances. [SCREENSHOT11]
* Evidence that Prometheus and AlertManager send alerts when certain conditions exist in the EC2 instance. [SCREENSHOT12]


# Section 3: files
## Surface critical server errors for diagnosis using centralized logging.
* Evidence of Prometheus Server. [URL05]
  * [URL05](./URL05.txt)
* Evidence that Prometheus is monitoring memory, cpu and disk usage of EC2 instances. [SCREENSHOT11]
  * [SCREENSHOT11](./screenshots/)
* Evidence that Prometheus and AlertManager send alerts when certain conditions exist in the EC2 instance. [SCREENSHOT12]
  * [SCREENSHOT12](./screenshots/)

## Files Included
* [`.circleci`](./.circleci)  
* [`backend`](./backend)
* [`frontend`](./frontend)  
* [`util`](./util)  
* [`.gitignore`](./.gitignore)  
* [`Screenshots`](./screenshots/)  
* [`presentation.pdf`](./presentation.pdf)  
* [`URL01.txt`](./URL01.txt)  
* [`URL02.txt`](./URL02.txt)  
* [`URL03.txt`](./URL03.txt)  
* [`URL04.txt`](./URL04.txt)  
* [`URL05.txt`](./URL05.txt)  
* [`README.md`](./README.md)  
* [`LICENSE.md`](./LICENSE.md)  

## License
* [**License**](./LICENSE.md)
