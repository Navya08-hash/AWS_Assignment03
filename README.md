# AWS_Assignment03
# AWS Networking, RDS & Serverless Contact Form

## Overview

This project demonstrates fundamental AWS networking, database connectivity, and serverless application development. It includes setting up a VPC with public and private subnets, connecting an Amazon RDS MySQL database to an EC2 application, and creating a serverless contact form using AWS Lambda and API Gateway.

---

## 1. Setup a VPC with Public & Private Subnets

### Tasks

- Created an Amazon VPC.
- Configured public and private subnets.
- Launched EC2 instances within the required subnets.
- Configured inbound and outbound security rules.
- Configured network connectivity between the required AWS resources.

### AWS Services Used

- **Amazon VPC** — Provides an isolated virtual network.
- **Amazon EC2** — Provides compute instances within the VPC.
- **Security Groups** — Control inbound and outbound traffic to resources.

### Network Architecture

```text
                    AWS VPC
                       |
          ┌────────────┴────────────┐
          |                         |
     Public Subnet             Private Subnet
          |                         |
       EC2 Instance             EC2/Resources
          |
    Internet Gateway
          |
       Internet
```

---

## 2. Create and Connect AWS RDS Database

### Tasks

- Created an Amazon RDS MySQL database.
- Configured the database within the VPC.
- Configured security group rules for database connectivity.
- Connected the RDS database with a sample application hosted on EC2.
- Tested database connectivity.

### AWS Service Used

**Amazon RDS** — Provides a managed relational database service without requiring manual database server management.

### Connection Flow

```text
EC2 Application
      |
      | MySQL Connection
      ↓
Amazon RDS
   MySQL Database
```

---

# 3. Mini Project — Serverless Contact Form

## Project Description

A serverless contact form was created using AWS Lambda and Amazon API Gateway. The form data is sent to an API endpoint, which invokes a Lambda function to process the submitted information.

### AWS Services Used

- **AWS Lambda** — Processes the contact form data without requiring a server.
- **Amazon API Gateway** — Provides an HTTP API endpoint for the Lambda function.

### Architecture

```text
Contact Form
     |
     | HTTP Request
     ↓
API Gateway
     |
     | Invoke
     ↓
AWS Lambda
     |
     ↓
Process Form Data
```

## Lambda Function

The Lambda function receives the request from API Gateway, processes the submitted form data, and returns an appropriate response.

Example response:

```json
{
  "message": "Contact form submitted successfully"
}
```

## API Testing

The API Gateway endpoint was tested using:

- Postman / Web Browser
- HTTP request
- Sample contact form data

### Sample Request

```json
{
  "name": "Test User",
  "email": "test@example.com",
  "message": "Hello from the contact form!"
}
```

### Expected Result

```json
{
  "message": "Contact form submitted successfully"
}
```

---

# Learning Outcomes

Through this project, I gained hands-on experience with:

- AWS VPC networking fundamentals
- Public and private subnet configuration
- EC2 deployment
- Security group configuration
- Amazon RDS MySQL
- EC2-to-RDS connectivity
- AWS Lambda
- Amazon API Gateway
- Serverless application architecture
- API testing using Postman/browser

---

# Conclusion

This project provided practical experience in designing AWS network infrastructure, connecting applications with managed databases, and building a serverless API using Lambda and API Gateway.
