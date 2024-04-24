**Shell Script to report usage of AWS in Project**
Written a Shell Script to report the usage of AWS in project like listing the S3 Buckets, IAM Users, EC2 Instances and Lambda. Also Integrate the Shell Script with CronJob.


#!/bin/bash
############################
# Author: Aditya Kumar
# Date  : 24-04-2024
#
# Shell script for tracking the resource usage in AWS mainly for AWS S3, IAM, EC2, Lambda
#
# Version : V1
#
############################

set -x # Debug Mode

# Listing the AWS S3 buckets and saving the information in a file format
aws s3 ls > resourceTracker

aws ec2 describe-insatnces | jq '.Resouce[].Instance[].InstanceId'
# Here in AWS EC2 jq is for JSON file & if there is YAML file then we will using yq.

aws lambda list-functions >>> resourceTracker

# Listing the AWS IAM Users.
aws iam list-users



![AWS_Resource_Usage](https://github.com/Aditya9119/AWS_Usage/assets/102175630/c1965f13-3257-4007-b0d1-cf491819124a)
