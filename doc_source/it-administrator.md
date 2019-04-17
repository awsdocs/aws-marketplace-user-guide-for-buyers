# Creating a Private Marketplace IT Administrator<a name="it-administrator"></a>

 You can create an IT administrators group to manage your company’s private marketplace settings\. Administrators for the private marketplace can control the look\-and\-feel of the private marketplace UI and can control what products users can subscribe to\. You can also enable access to the private marketplace as part of an organization created in [AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/)\. Examples of tasks you can perform as an administrator of a private marketplace include: 
+ Enabling and disabling a private marketplace for your company\.
+ Adding products to your company's private marketplace\.
+ Removing products from your company's private marketplace\.
+ Configuring the look and feel of your company's private marketplace\.

You grant IAM permissions to administer your private marketplace by attaching the **AWSPrivateMarketplaceAdminFullAccess** policy to an IAM user, group, or role\. We recommend using a group or role\. See [IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) for more information on recommended practices for using IAM\.

For your reference we have included the contents of the **AWSPrivateMarketplaceAdminFullAccess** policy here:

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:CreatePrivateMarketplace",
                "aws-marketplace:CreatePrivateMarketplaceProfile",
                "aws-marketplace:UpdatePrivateMarketplaceProfile",
                "aws-marketplace:StartPrivateMarketplace",
                "aws-marketplace:StopPrivateMarketplace",
                "aws-marketplace:AssociateProductsWithPrivateMarketplace",
                "aws-marketplace:DisassociateProductsFromPrivateMarketplace",
                "aws-marketplace:DescribePrivateMarketplaceProfile",
                "aws-marketplace:DescribePrivateMarketplaceStatus",
                "aws-marketplace:ListPrivateMarketplaceProducts",
                "aws-marketplace:DescribePrivateMarketplaceProducts"
            ],
            "Resource": [
                "*"
            ]
        }
    ]
 }
```