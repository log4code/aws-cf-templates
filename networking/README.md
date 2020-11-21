# Usage examples

## VPC

From the CLI:

```
 aws cloudformation create-stack --stack-name <vpcName> --template-body file://vpc.yml --profile <profileName>
 ```
 
 Required IAM permissions:
 
 ```
ec2:CreateTags
ec2:CreateVpc
ec2:DescribeVpcs
ec2:ModifyVpcAttribute
cloudformation:ValidateTemplate
 ```
