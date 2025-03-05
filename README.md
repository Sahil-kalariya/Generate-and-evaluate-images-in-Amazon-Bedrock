# What is it about ?

Generate and evaluate images in Amazon Bedrock with Amazon Titan Image Generator G1 v2 and Anthropic Claude 3.5 Sonnet


## Requirements

An AWS account to create and manage the necessary AWS resources for this solution.

Amazon Titan Image Generator G1 v2 and Anthropic Claude 3.5 Sonnet models enabled on Amazon Bedrock in AWS Region us-east-1.

IAM user with appropriate permissions.

## Steps

You can build the solution architecture using AWS CloudFormation.

A single YAML file contains the infrastructure, including AWS Identity and Access Management (IAM)  users, policies, API methods, the S3 bucket, and the Lambda function code.

Upload yml file from repo in S3

Sign in to the AWS Management Console as an IAM administrator or appropriate IAM user.

Choose Launch Stack to deploy the CloudFormation template.

Select yml file url which you uploaded in S3 and paste 

Choose Next.

In the Parameters section, enter the following:

A name for the new S3 bucket that will receive the images (for example, image-gen-your-initials)

The name of an existing S3 bucket where access logs will be stored.

A token that you will use to authenticate your API (a string of your choice)

After entering the parameters, choose Next.
Choose Next again.
Acknowledge the creation of IAM resources and choose Submit.
When the stack status is CREATE_COMPLETE, navigate to the Outputs tab and find the API information. Copy the ApiId, the ApiUrl and ResourceId to a safe place and continue to test.

## Test the solution using the console
Complete the following steps to test the solution using the console:

On the API Gateway console, choose APIs in the navigation pane.

On the APIs list, choose BedrockImageGenEval.

In the Resources section, select the POST method below /generate-image.

Choose the Test tab in the method execution settings.

In the Request body section, enter the following JSON structure:
{ “prompt”:”your prompt” }

Choose Test.

