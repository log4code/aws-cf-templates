# Usage examples

## VPC

### vpc.yml

**Template details**
```
{
    "Parameters": [
        {
            "ParameterKey": "VpcCIDR",
            "DefaultValue": "10.192.0.0/16",
            "NoEcho": false,
            "Description": "The IP range (CIDR notation) for this VPC"
        },
        {
            "ParameterKey": "EnvironmentName",
            "DefaultValue": "BasicVpc",
            "NoEcho": false,
            "Description": "An environment name to tag to resources"
        }
    ],
    "Description": "This is a template to deploy a simple VPC"
}

```

To use the defaults:
```
 aws cloudformation create-stack --stack-name <vpcName> --template-body file://vpc.yml --profile <profileName>
 ```
 
 Using the parameters:
 ```
aws cloudformation create-stack --stack-name <vpcName> --template-body file://vpc.yml --parameters ParameterKey=EnvironmentName,ParameterValue=<EnvironmentName> ParameterKey=VpcCIDR,ParameterValue=<your CIDR range> --profile <profileName>
 ```
 
 
 Required IAM permissions:
 
 ```
ec2:CreateTags
ec2:CreateVpc
ec2:DescribeVpcs
ec2:ModifyVpcAttribute
cloudformation:ValidateTemplate
 ```
