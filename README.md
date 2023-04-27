# Schedule ECS Fargate Tasks to stop and start with Amazon EventBridge Rule.

This is a simple CloudFormation that sets up stopping and starting of an existing ECS service by a schedule for specified tasks.

We have confirmed operation in the following environments
- ECS(Fargate type) 

## Overview of AWS resources to be created
The following resources will be created when this CloudFormation is deployed.

![Resource Overview](image/resources.svg)

List of resources to be created
- AWS Event Rule
- AWS Lambda(and permission)
- IAM Role for Lambda

## Setup
Extract ecs-schedule.yaml from the AWS Management Console or AWS CLI.

Parameters
- NamePrefix: Prefix
- EcsClusterName: ECS cluster name
- EcsServiceName: ECS service name
- EcsClusterArn: ECS cluster ARN
- StopScheduleExpression: CRON expression specifying the time to stop (UTC)
- StartScheduleExpression: CRON expression for time to start (UTC)
- StopDesiredCount: number specified for DesiredCount to stop (stop=0)
- StartDesiredCount: number specified for DesiredCount to starting

[Schedule Expressions for Rules] &nbsp;
https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/ScheduledEvents.html



