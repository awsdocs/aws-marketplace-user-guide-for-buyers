# Using AMI aliases<a name="buyer-ami-aliases"></a>

An Amazon Machine Image \(AMI\) is identified with an `AMI ID`\. You can use the `AMI ID` to indicate which AMI you want to use when launching a product\. The `AMI ID` has the form `ami-<identifier>`, for example, ami\-123example456\. Each version of each product in each AWS Region has a different AMI \(and different `AMI ID`\)\.

When you launch a product from AWS Marketplace, the `AMI ID` is automatically filled in for you\. Having the `AMI ID` is useful if you want to automate launching products from the AWS Command Line Interface \(AWS CLI\) or by using Amazon Elastic Compute Cloud \(Amazon EC2\)\. You can find the `AMI ID` when you configure your software at launch time\. For more information, see [Step 3: Configuring your software](buyer-getting-started.md#step-3-configure-your-software)\. 

The `Ami Alias` is also in the same location as the `AMI ID`, when configuring your software\. The `Ami Alias` is a similar ID to the `AMI ID`, but it's easier to use in automation\. An `AMI alias` has the form `aws/service/marketplace/prod-<identifier>/<version>` , for example,` aws/service/marketplace/prod-1234example5678/12.2`\. You can use this `Ami Alias` Id in any Region, and AWS automatically maps it to the correct Regional `AMI ID`\. 

If you want to use the most recent version of a product, use the term **latest** in place of the version in the `AMI alias` so that AWS chooses the most recent version of the product for you, for example, **aws/service/marketplace/prod\-1234example5678/latest**\.

**Warning**  
Using the **latest** option gives you the most recently released version of the software\. However, use this feature with caution\. For example, if a product has versions 1\.x and 2\.x available, you might be using 2\.x\. However, the most recently released version of the product might be a bug fix for 1\.x\.

## Examples of using AMI aliases<a name="buyer-ami-alias-examples"></a>

AMI aliases are useful in automation\. You can use them in the AWS CLI or in AWS CloudFormation templates\.

The following example shows using an AMI alias to launch an instance by using the AWS CLI\.

```
aws ec2 run-instances
--image-id resolve:ssm:/aws/service/marketplace/<identifier>/version-7.1
--instance-type m5.xlarge
--key-name MyKeyPair
```

The following example shows a CloudFormation template that accepts the AMI alias as an input parameter to create an instance\.

```
AWSTemplateFormatVersion: 2010-09-09

Parameters:
    AmiAlias:
        Description: AMI alias
        Type: 'String'
        
Resources:
    MyEC2Instance:
        Type: AWS::EC2::Instance
        Properties:
            ImageId: !Sub "resolve:ssm:${AmiAlias}"
            InstanceType: "g4dn.xlarge"
            Tags:
                -Key: "Created from"
                 Value: !Ref AmiAlias
```