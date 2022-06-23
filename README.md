# static-cloudformation-template
## Pre setup instructions
Create a hosted zone in route53,and add main domain records


## Setup instructions

Change following variables in these files 
```bash
  # aws/cloudformation.yaml
  Domain: your-domain.com
  BucketName: your-bucket-name
  PolicyName: your-policy-name
  UpdateIamUserName: your-username
```

Move your static content inside build directory

Create a `release` branch and push latest changes to be deploy

Command to deploy
```bash
aws cloudformation deploy --capabilities CAPABILITY_NAMED_IAM --template-file ./path-to-your-template.yml --stack-name your-stack-name --parameter-overrides Env=prod HostedZoneId=your-hosted-id --tags app=your-tag env=prod
```
