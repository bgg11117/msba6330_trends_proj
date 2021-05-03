# Project Infrastructure Setup on AWS

## Overview of the Voice Pipeline 
![image](https://user-images.githubusercontent.com/76879882/116840304-f6459280-ab9a-11eb-8357-887cf56dd01a.png)

## Prerequisite
Amazon Developer Account (free) is needed to build Alexa skills

## Step 1: Create Baseline Resources 
A CloudFormation template is needed to create baseline resources, which include IAM Roles, IAM Policies, a DynamoDB table, and a CloudWatch Event rule. 
Template ref: https://github.com/awslabs/voice-powered-analytics

## Step 2: Load Data in S3 
Create a S3 bucket and load the "yelp" dataset in. 

## Step 3: Create a Query to extract pre-identified metrics using Athena
Create an external table "yelp" in the default database so that we can query S3 at rest. 

Create queries to extract pre-identified metrics, copy these queries to a text editor to save later.

## Step 4: Create a Lambda function to query Athena 
Create a lambda function from scratch and name it as "vpa_lambda_athena_poller"; under Role leave the default value of Choose an existing role and nder existing role, select "VPALambdaAthenaPollerRole"

Under "code", copy and paste the Function code (in python) provided: https://github.com/bgg11117/msba6330_trends_proj/blob/main/voice_powered_analytics_code.ipynb 

Under "configuration", click on "Environment" and set up environment variables listed below 
![image](https://user-images.githubusercontent.com/76879882/116839025-49691680-ab96-11eb-90c9-7a754b4aa665.png)

Under "configuration", click on "Triggers" and select "CloudWatch Events". We will use the CloudWatch Event Rule created from the CloudFormation template to trigger this Lambda.

Create a test event to test this lambda and see if the returned query result is accurate. 

## Step 5: Build Alexa Skills (Set up Voice User Interface) 
Create Alexa Skills from scratch and set the invocation name as "voice powered analytics". The invocation name serves as opening up an interaction with a custom skill. 

Create a custom intent and name it as "WhatsMyMetric". A intent represents an action that fulfills a user's request. 

Next add utterances to our intent. This triggers an invoke of your intent through your user's voice. 

Parameterize slot and for the slot value, enter the value of the metric used from the Athena_Poller Lambda function's environment variable: metric (e.g. Average review count).

## Step 6: Build Alexa skills (Configure the backend)
Create a Lambda function that contains all of our logic for the skill.
ref: https://github.com/awslabs/voice-powered-analytics/blob/master/README-Alexav2.md 

## Step 7: COnnect Alexa to the Lambda Function
Copy the Lambda ARN from the Lambda function created in previous step, and paste it to the "Default Region" in the SAVEPOINT in Alexa Skill, click Save. 

## Congradulation, you are all set and ready to test your skill 
![image](https://user-images.githubusercontent.com/76879882/116908351-66d6c880-ac08-11eb-93ca-0f336c0a5bf4.png)



