# Simple Storage Service (S3) on AWS
AWS S3 is a storage service offered by Amazon Web Services for storing any data in a way that is flexible, cost-effective, highly available, and persistent. Examples of companies that use AWS S3 include Trello, Airbnb, and Netflix. 

![amazon-s3-setup](https://user-images.githubusercontent.com/88166874/132367770-a9541c44-42fe-4fda-a9c7-46cb211f3bf9.png)

## Prerequisites
- Open up Git Bash as Administrator
- ssh into your app EC2 instance (follow instructions from [the VPC repo and related repos](https://github.com/am93596/SRE_AWS_VPC__and_Networking))
- Run the following commands from inside the EC2 instance@
```bash
sudo apt-get update -y
sudo apt-get upgrade -y
sudo apt-get install python
sudo apt-get install python3-pip
python --version
alias python=python3    # will have to create again if i close terminal; need to make it persistent as env var
python3 -m pip install awscli
```  

## Configuring AWS
- Enter the following command, and then paste in the `Access Key` and `Secret Key` when they are asked for. The region is `eu-west-1`, and the data type is `json`
- `aws configure`  

## Setting Up A Bucket
- Use the following command to list the current buckets:
- `aws s3 ls`
- Then make a new bucket using `aws s3 mb s3://sreamy` -> `mb` means make bucket, and `sreamy` is the name of the new bucket
- To copy a file from your current directory to the bucket, use `aws s3 cp README.md s3://sreamy`  

## Downloading A File From A Bucket
- To download a file from your bucket into your current directory, use `aws s3 cp s3://sreamy/README.md ./`  

## Syncing File Changes From Local Version To S3 Version
- To sync a file from your bucket, go to the directory for the file, and use the following command: `aws s3 sync . s3://sreamy`  

## Deleting A File From A Bucket
- To delete a file from an S3 Bucket, use the following command: `aws s3 rm s3://sreamy/README.md`  

## Deleting A Bucket
- If the bucket is empty, use the following command: `aws s3 rb s3://sreamy`
- If the bucket still has files in it, use `aws s3 rb s3://sreamy --force`

# Python3 Boto Task
- Instructions:
```
Research the documentation on AWS/Python for python boto3 package to create and manage AWS S3 resources and complete all the following tasks:
  Setting up awscli and python Env with required dependencies
  S3 authentication setup - with aws configure on EC2
  Create S3 bucket using python-boto3
  Upload data/file to S3 bucket using python-boto3
  Retrieve content/file from S3 using python-boto3
  Delete Content from S3 using python-boto3
  Delete the bucket using python-boto3.**
HINT: install and import boto3 - works with python3 and above
```
