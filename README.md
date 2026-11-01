# Automated Web Application Deployment using Jenkins CI/CD and Terraform on AWS

## Project Overview
This project demonstrates automated web application deployment using Jenkins CI/CD and Infrastructure as Code (IaC) using Terraform on AWS.

## Technologies Used
- AWS EC2
- Jenkins
- Git and GitHub
- Terraform
- Amazon S3
- Nginx
- Ubuntu Linux

## Architecture
GitHub Repository → Jenkins Pipeline → Checkout → Build → Test → Deploy → Nginx Web Server

Terraform separately provisions an Amazon S3 bucket with versioning enabled.

## Project Structure
```text
jenkins-terraform-mini-project/
├── index.html
├── Jenkinsfile
├── terraform/
│   └── main.tf
└── README.md
```

## Jenkins CI/CD Pipeline
The Jenkins pipeline consists of four stages:

1. **Checkout:** Retrieves application source code from GitHub.
2. **Build:** Prepares the application files.
3. **Test:** Validates the generated HTML file.
4. **Deploy:** Deploys the application to the Nginx web server.

## Terraform Infrastructure
Terraform provisions:
- An Amazon S3 bucket with a unique name.
- S3 bucket versioning enabled.
- AWS resource tags for project identification.

**AWS Region:** ap-southeast-2 (Sydney)

## Deployment Result
The application was successfully deployed using Jenkins and is accessible through the EC2 public IP.

## Terraform Commands
```bash
terraform init
terraform validate
terraform plan
terraform apply
```

## Outcome
Successfully implemented a Jenkins CI/CD pipeline and Terraform-based AWS infrastructure provisioning, demonstrating automated deployment and Infrastructure as Code.
