# Start EC2 Instance Action

## Description
Start EC2 instance(s).

## Syntax
```
AWS.StartEC2Instance Ec2Client: `` InstanceIds: `` StartingEc2Instances=> StartingEc2Instances
```

## Parameters
- Ec2Client (Required): The EC2 client
- InstanceIds (Required): The instance IDs to start

## Output
- StartingEc2Instances: List of Instance state changes

## Exceptions
- Authentication failed
- Unauthorized operation
- Invalid instance ID
- Insufficient capacity
- Amazon service request failed