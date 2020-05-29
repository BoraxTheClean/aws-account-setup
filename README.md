# AWS Account Setup

[One Click Deploy Link](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/quickcreate?templateURL=https://owen-public-production-bucket.s3.amazonaws.com/aws-account-bootstrap/template.yaml&stackName=BootStrapStack&param_AlarmThreshold=10&param_UserName=MyUser)

This repo contains a cloudformation template to deploy to your fresh AWS account. It will create an IAM user to use and a Budget to notify you if you exceed a threshold of spend.

It is an AWS best practice to use IAM User accounts instead of root credentials. The IAM User provisioned will have administrator access.

## Parameters

```yaml
  BudgetThreshold:
    Type: String
    Description: Alarm if AWS spend is over this threshold in dollars.
    Default: 10

  Email:
    Type: String
    Description: The email to which a billing notification will be sent.

  UserName:
    Type: String
    Description: The name of the IAM user to create.

  Password:
    Type: String
    NoEcho: True
    Description: The password for your IAM user. You can change it later.
```

When deploying the stack, you'll want to set these parameters to fit your use case:

	1. _BudgetThreshold_ This is a monthly budget, in USD. You'll recieve email notifications when you exceed 80% or 100% of the budget. The threshold is adjustable, so if you set it to $3 and later find $10 is more useful, you can update the Stack with a new value to update it.
	2. _Email_ This email will recieve billing notifications based on your budget.
	3. _UserName_ You'll use this value to log in to the console with your IAM User this stack creates.
	4. _Password_ You'll use this password to log in. This password won't be visible in the console after you enter it.

## Where to Find Me

[If you liked this free resource, be free to check out my other courses at GumRoad!](https://store.owen.dev)

[All my links are on my personal site.](https://owen.dev)

Email me at owen@owen.dev, follow me on GitHub, and [Twitter](https://twitter.com/AWSOwen)

