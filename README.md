# htan

## Data Ingress Document
https://ncihtan.github.io/HTAN-Data-Ingress-Docs/

## Getting started
Stanford uses AWS for data upload into the htan-dcc-stanford S3 bucket.
Historically, some older datasets were uploaded to Synapse's own S3 bucket (e.g. syn23594433), so they are not visible from the htan-dcc-stanford S3 bucket.

To get access to the S3 bucket as admin, contact Keith Bettinger to gain access to the sub-account gbsc-aws-prj-htan. Then, go to https://us-east-1.console.aws.amazon.com/iamv2/home#/users and create a new IAM user from that sub-account. The permission policies can be copied from existing users during new user creation.

To connect to the bucket, ssh to scg:

    ssh [username]@login.scg.stanford.edu 

Use the following commands:

    module load aws-cli
The first time only, configure your credentials, using the information for the newly created user.

    aws configure

At that point, send an email to the HTAN liaison (https://ncihtan.github.io/HTAN-Data-Ingress-Docs/dcc-liaison.html) and provide your IAM user information.

Once you have been given access, you will be able to confirm by running an ls command through the AWS command line interface on scg:

    ssh [username]@login.scg.stanford.edu 
    module load aws-cli
    aws s3 ls s3://htan-dcc-stanford/

If you see a list of folders, you hace access.
You can use 

    aws s3 help

for a list of commands.

## Synapse documentation
https://help.synapse.org/docs/