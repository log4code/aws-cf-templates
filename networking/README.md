# Usage examples

## VPC

### vpc.yml

**Template details**
```
{
    "Parameters": [
        {
            "ParameterKey": "PrivateSubnet1CIDR",
            "DefaultValue": "10.192.20.0/24",
            "NoEcho": false,
            "Description": "The IP range (CIDR notation) for the private subnet in the first Availability Zone"
        },
        {
            "ParameterKey": "PublicSubnet2CIDR",
            "DefaultValue": "10.192.11.0/24",
            "NoEcho": false,
            "Description": "The IP range (CIDR notation) for the public subnet in the second Availability Zone"
        },
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
        },
        {
            "ParameterKey": "PrivateSubnet2CIDR",
            "DefaultValue": "10.192.21.0/24",
            "NoEcho": false,
            "Description": "The IP range (CIDR notation) for the private subnet in the second Availability Zone"
        },
        {
            "ParameterKey": "PublicSubnet1CIDR",
            "DefaultValue": "10.192.10.0/24",
            "NoEcho": false,
            "Description": "The IP range (CIDR notation) for the public subnet in the first Availability Zone"
        }
    ],
    "Description": "This is a template to deploy a simple VPC"
}


```
 
To use the defaults:
```
 aws cloudformation create-stack --stack-name <vpcName> --template-body file://vpc.yml --profile <profileName>
 ```
 
 Using the parameters (example):
 ```
aws cloudformation create-stack --stack-name <vpcName> --template-body file://vpc.yml --parameters ParameterKey=EnvironmentName,ParameterValue=<EnvironmentName> ParameterKey=VpcCIDR,ParameterValue=<your CIDR range> --profile <profileName>
 ```
 
 
 Required IAM permissions:
 
 ```
ec2:CreateTags (cloudformation)
ec2:CreateVpc (vpc)
ec2:CreateSubnet (subnets)
ec2:DescribeVpcs (vpc)
ec2:DescribeAvailabilityZones (subnets)
ec2:DescribeAccountAttributes (subnets)
ec2:ModifyVpcAttribute (vpc)
ec2:ec2:DescribeSubnets (subnets)
ec2:ModifySubnetAttribute (subnets)
cloudformation:ValidateTemplate (cloudformation)
ec2:CreateInternetGateway (internetgateway)
ec2:DescribeInternetGateways (internetgateway)
ec2:AttachInternetGateway (internetgateway)

 ```
