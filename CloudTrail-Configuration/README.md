## CloudTrail Configuration

We can monitor and evaluate telemetry using AWS Cloudtrail. After setting up the attack vector, we may now configure Cloudtrail.

A test sample to check in for user creation:

![CloudTrailLookup](./CreateUserLookup.png)

## Step One: Creating Trail

## Step Two: Setting up S3 Bucket

We can set up an AWS S3 Bucket to store the incoming logs from cloudtrail and use this later for log analysis and relating each telemetry to understand what kind of attack has been launched against the Cloud Environment. 
