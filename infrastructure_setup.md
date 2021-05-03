# Project Infrastructure Setup on AWS

## Step 1: Create Baseline Resources 
A CloudFormation template is needed to create baseline resources, which include IAM Roles, IAM Policies, a DynamoDB table, and a CloudWatch Event rule. 
Template ref: https://github.com/awslabs/voice-powered-analytics

## Step 2: Load Data in S3 
Create a S3 bucket and load the "yelp" dataset in. 

## Step 3: Create a Query to extract pre-identified metrics using Athena
Create an external table "yelp" in the default database so that we can query S3 at rest. 
Create queries to extract pre-identified metrics, copy these queries to a text editor to save later.

## Step 4: Create a Lambda function to query Athena 
Create a lambda function from scratch and name it as vpa_lambda_athena_poller; under Role leave the default value of Choose an existing role and nder existing role, select VPALambdaAthenaPollerRole
Function code (in python) is provided: (some link) 

![image](https://user-images.githubusercontent.com/76879882/116839025-49691680-ab96-11eb-90c9-7a754b4aa665.png)
