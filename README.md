

### Creating our VPC
```
aws ec2 create-vpc --cidr-block 10.10.0.0/18 --no-amazon-provided-ipv6-cidr-block --tag-specifications 'ResourceType=vpc,Tags=[{Key=Name,Value=kma-genesis},{Key=Lesson,Value=public-clouds}]' --query Vpc.VpcId --output text
```


### Getting VPC id
```
aws ec2 describe-vpcs | grep "VpcId" # get VPC ID
```


### Creating 3 subnets (using previous command output as $VPC_ID)
```
aws ec2 create-subnet --vpc-id $VPC_ID --availability-zone us-east-1a --cidr-block 10.10.1.0/24
```
```
aws ec2 create-subnet --vpc-id $VPC_ID --availability-zone us-east-1b --cidr-block 10.10.2.0/24
```
```
aws ec2 create-subnet --vpc-id $VPC_ID --availability-zone us-east-1c --cidr-block 10.10.3.0/24
```






