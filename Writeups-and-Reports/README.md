## Attack Vector 1: IAM-Backdoor-User (Persistence Technique)

Using Stratus's IAM Backdoor user, is a persistence technique whereby it establishes persistence by creating an access key on an existing IAM user.

**Objective:* Detect an access key being created for an existing IAM user.

Simulation: aws.persistence.iam-backdoor-user. Explain that warmup creates the target user and detonation creates its access key.

Detection: using the following Query within AWS Cloudwatch: 

`SOURCE logGroups(namePrefix: [], class: "STANDARD") START=-1h END=0s |
fields @timestamp, requestParameters.userName, userIdentity.type, userIdentity.accountId, userIdentity.roleArn, eventName, userIdentity.arn
| filter eventName in ["CreateUser", "AttachUserPolicy", "CreateAccessKey"]
| sort @timestamp desc
| limit 10000`
