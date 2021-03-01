# AWS Transit Gateway flows secured by AWS Gateway Load Balancer and a Active/Active Fortigate

This is placeholder documentation until the final version of the documentation is uploaded.

## Included in this template
This is a cloudformation template that will create the following
- 3 VPC
  - Security hub VPC which includes:
    - 1x Gateway Load Balancer
    - 2x Gateway Load Balancer endpoints in two availability zones
    - 2x FortiGates in standalone Active/Active (firmware 6.4.4 with PAYG)
    - 1x Internet Gateway
  - Spoke VPC which includes:
    - 1x Linux VM directly accessible from the internet for testing
  - Spoke VPC which includes:
    - 1x Linux VM
- 1 Transit Gateway
- All the necessary routing tables

## Prerequisites to deploy
1. The parameter "MyIPForAccess" is used to create a route in the spoke VPC to directly access the linux VM.
2. The parameter "InitS3Bucket" and "InitS3BucketRegion" are required to generate the configuration files of the FortiGates. This S3 bucket needs to be made before deploying the template and require default public access.
