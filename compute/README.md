# Usage examples

## EC2

### simpleec2.yml


 Using the parameters (example):
 ```
$ aws cloudformation create-stack --stack-name <stackName> --template-body file://simpleec2.yml --parameters ParameterKey=SecurityGroupIds,ParameterValue=<SecurityGroupIds> ParameterKey=SubNetId,ParameterValue=<subnetId> --profile <profileName>
 ```



 Required IAM permissions:
 
 ```
 ec2:DescribeImages (instance)
 ec2:DescribeInstances (instance)
 ec2:RunInstances (instance)
 ssm:GetParameters (instance)
 ```