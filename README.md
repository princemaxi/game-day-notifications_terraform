# NBA Game Day Notification System

## Project Overview

This project is an alert system that sends real-time NBA game day score notifications to subscribed users via SMS/Email. It leverages Amazon SNS, AWS Lambda, Python, Amazon EventBridge, and NBA APIs to provide sports fans with up-to-date game information. The project demonstrates the use of Infrastructure as Code (IaC) by leveraging Terraform to automate the deployment and destruction of this solution in seconds.

## Features

- Fetches live NBA game scores using an external API.
- Sends formatted score updates to subscribers via SMS/Email using Amazon SNS.
- Automated scheduling for regular updates using Amazon EventBridge.
- Secure architecture following the principle of least privilege for IAM roles.

## Prerequisites

- Free account with subscription and API Key from [SportsData.io](https://sportsdata.io/)
- Personal AWS account with a basic understanding of AWS and Python
- AWS CLI installed and configured
- Terraform CLI (>= 1.10.5) installed on your local environment

## Technical Architecture

![image](https://github.com/user-attachments/assets/b6484861-8cdf-42f2-aa3f-92a30c4fef4e)

## Technologies Used

- **Cloud Provider:** AWS
- **Infrastructure as Code:** Terraform
- **Core AWS Services:** SNS, Lambda, EventBridge, IAM
- **External API:** NBA Game API (SportsData.io)
- **Programming Language:** Python 3.x
- **Security:** Least privilege IAM policies for Lambda, SNS, and EventBridge

## Project Structure

![image](https://github.com/user-attachments/assets/ec6110b2-6229-48cc-907c-28fb22bde2ca)


## Setup Instructions

### Clone the Repository

```bash
git clone https://github.com/princemaxi/game-day-notifications_terraform.git
cd game-day-notifications

## Store API Key as a Secret in AWS Parameter Store

aws ssm put-parameter --name "nba-api-key" --value "<API_KEY>" --type "SecureString"

## Deploy Infrastructure with Terraform
Initialize Terraform

terraform init

Format Terraform files

terraform fmt

Validate Terraform configuration
terraform validate

Preview changes before applying
terraform plan

Apply Terraform configuration
terraform apply

Subscribe to SNS Notifications
Navigate to the SNS Topic in AWS.

Click on Create Subscription.

Select a protocol:

Email: Enter a valid email address.

SMS: Enter a valid phone number (e.g., +1234567890).

Click Create Subscription.

For Email: Check your inbox and confirm the subscription.

Destroy Infrastructure (if needed)
terraform destroy




