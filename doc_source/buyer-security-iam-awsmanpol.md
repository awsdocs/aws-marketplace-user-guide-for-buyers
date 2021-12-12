# AWS managed policies for AWS Marketplace buyers<a name="buyer-security-iam-awsmanpol"></a>

To add permissions to users, groups, and roles, it is easier to use AWS managed policies than to write policies yourself\. It takes time and expertise to [create IAM customer managed policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create-console.html) that provide your team with only the permissions they need\. To get started quickly, you can use our AWS managed policies\. These policies cover common use cases and are available in your AWS account\. For more information about AWS managed policies, see [AWS managed policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-vs-inline.html#aws-managed-policies) in the *IAM User Guide*\.

AWS services maintain and update AWS managed policies\. You can't change the permissions in AWS managed policies\. Services occasionally add additional permissions to an AWS managed policy to support new features\. This type of update affects all identities \(users, groups, and roles\) where the policy is attached\. Services are most likely to update an AWS managed policy when a new feature is launched or when new operations become available\. Services do not remove permissions from an AWS managed policy, so policy updates won't break your existing permissions\.

Additionally, AWS supports managed policies for job functions that span multiple services\. For example, the **ViewOnlyAccess** AWS managed policy provides read\-only access to many AWS services and resources\. When a service launches a new feature, AWS adds read\-only permissions for new operations and resources\. For a list and descriptions of job function policies, see [AWS managed policies for job functions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_job-functions.html) in the *IAM User Guide*\.

This section lists each of the policies used to manage buyer access to AWS Marketplace\. For information about seller policies, see [AWS managed policies for AWS Marketplace sellers](https://docs.aws.amazon.com/marketplace/latest/userguide/security-iam-awsmanpol.html) in the *AWS Marketplace Seller Guide*\.

**Topics**
+ [AWS managed policy: AWSMarketplaceFullAccess](#security-iam-awsmanpol-awsmarketplacefullaccess)
+ [AWS managed policy: AWSMarketplaceImageBuildFullAccess](#security-iam-awsmanpol-awsmarketplaceimagebuildfullaccess)
+ [AWS managed policy: AWSMarketplaceLicenseManagementServiceRolePolicy](#security-iam-awsmanpol-awsmarketplacelicensemanagementservicerolepolicy)
+ [AWS managed policy: AWSMarketplaceManageSubscriptions](#security-iam-awsmanpol-awsmarketplacemanagesubscriptions)
+ [AWS managed policy: AWSMarketplaceProcurementSystemAdminFullAccess](#security-iam-awsmanpol-awsmarketplaceprocurementsystemadminfullaccess)
+ [AWS managed policy: AWSMarketplaceRead\-only](#security-iam-awsmanpol-awsmarketplaceread-only)
+ [AWS managed policy: AWSPrivateMarketplaceAdminFullAccess](#security-iam-awsmanpol-awsprivatemarketplaceadminfullaccess)
+ [AWS managed policy: AWSPrivateMarketplaceRequests](#security-iam-awsmanpol-awsprivatemarketplacerequests)
+ [AWS Marketplace updates to AWS managed policies](#security-iam-awsmanpol-updates)

## AWS managed policy: AWSMarketplaceFullAccess<a name="security-iam-awsmanpol-awsmarketplacefullaccess"></a>

You can attach the `AWSMarketplaceFullAccess` policy to your IAM identities\.

This policy grants administrative permissions that allow full access to AWS Marketplace and related services, both as a buyer and a seller\. These permissions include the ability to subscribe and unsubscribe to AWS Marketplace software, manage AWS Marketplace software instances from the AWS Marketplace, creating and managing private marketplace in your account, as well as access to Amazon EC2, AWS CloudFormation, and Amazon EC2 Systems Manager\.



**Permissions details**

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:*",
                "cloudformation:CreateStack",
                "cloudformation:DescribeStackResource",
                "cloudformation:DescribeStackResources",
                "cloudformation:DescribeStacks",
                "cloudformation:List*",
                "ec2:AuthorizeSecurityGroupEgress",
                "ec2:AuthorizeSecurityGroupIngress",
                "ec2:CreateSecurityGroup",
                "ec2:CreateTags",
                "ec2:DescribeAccountAttributes",
                "ec2:DescribeAddresses",
                "ec2:DeleteSecurityGroup",
                "ec2:DescribeImages",
                "ec2:DescribeInstances",
                "ec2:DescribeKeyPairs",
                "ec2:DescribeSecurityGroups",
                "ec2:DescribeSubnets",
                "ec2:DescribeTags",
                "ec2:DescribeVpcs",
                "ec2:RunInstances",
                "ec2:StartInstances",
                "ec2:StopInstances",
                "ec2:TerminateInstances"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "ec2:CopyImage",
                "ec2:DeregisterImage",
                "ec2:DescribeSnapshots",
                "ec2:DeleteSnapshot",
                "ec2:CreateImage",
                "ec2:DescribeInstanceStatus",
                "ssm:GetAutomationExecution",
                "ssm:UpdateDocumentDefaultVersion",
                "ssm:CreateDocument",
                "ssm:StartAutomationExecution",
                "ssm:ListDocuments",
                "ssm:UpdateDocument",
                "ssm:DescribeDocument",
                "sns:ListTopics",
                "sns:GetTopicAttributes",
                "sns:CreateTopic",
                "iam:GetRole",
                "iam:GetInstanceProfile",
                "iam:ListRoles",
                "iam:ListInstanceProfiles"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:ListBucket",
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::*image-build*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "sns:Publish",
                "sns:setTopicAttributes"
            ],
            "Resource": "arn:aws:sns:*:*:*image-build*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "iam:PassRole"
            ],
            "Resource": [
                "*"
            ],
            "Condition": {
                "StringLike": {
                    "iam:PassedToService": [
                        "ec2.amazonaws.com",
                        "ssm.amazonaws.com"
                    ]
                }
            }
        }
    ]
}
```

## AWS managed policy: AWSMarketplaceImageBuildFullAccess<a name="security-iam-awsmanpol-awsmarketplaceimagebuildfullaccess"></a>

You can attach the `AWSMarketplaceImageBuildFullAccess` policy to your IAM identities\.

This policy grants contributor permissions that allow full access to the AWS Marketplace private image build feature\. In addition to creating private images, it also provides permisions to add tags to images, and to launch and terminate Amazon EC2 instances\.

**Permissions details**

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:ListBuilds",
                "aws-marketplace:StartBuild",
                "aws-marketplace:DescribeBuilds"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": "ec2:TerminateInstances",
            "Resource": "*",
            "Condition": {
                "StringLike": {
                    "ec2:ResourceTag/marketplace-image-build:build-id": "*"
                }
            }
        },
        {
            "Effect": "Allow",
            "Action": "iam:PassRole",
            "Resource": [
                "arn:aws:iam::*:role/*Automation*",
                "arn:aws:iam::*:role/*Instance*"
            ],
            "Condition": {
                "StringEquals": {
                    "iam:PassedToService": [
                        "ec2.amazonaws.com",
                        "ssm.amazonaws.com"
                    ]
                }
            }
        },
        {
            "Effect": "Allow",
            "Action": [
                "ssm:GetAutomationExecution",
                "ssm:CreateDocument",
                "ssm:StartAutomationExecution",
                "ssm:ListDocuments",
                "ssm:UpdateDocument",
                "ssm:UpdateDocumentDefaultVersion",
                "ssm:DescribeDocument",
                "ec2:DeregisterImage",
                "ec2:CopyImage",
                "ec2:DescribeSnapshots",
                "ec2:DescribeSecurityGroups",
                "ec2:DescribeImages",
                "ec2:DescribeSubnets",
                "ec2:DeleteSnapshot",
                "ec2:CreateImage",
                "ec2:RunInstances",
                "ec2:DescribeInstanceStatus",
                "sns:GetTopicAttributes",
                "iam:GetRole",
                "iam:GetInstanceProfile"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:GetObject",
                "s3:ListBucket"
            ],
            "Resource": [
                "arn:aws:s3:::*image-build*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "ec2:CreateTags"
            ],
            "Resource": [
                "arn:aws:ec2:*::image/*",
                "arn:aws:ec2:*:*:instance/*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "sns:Publish"
            ],
            "Resource": [
                "arn:aws:sns:*:*:*image-build*"
            ]
        }
    ]
}
```

## AWS managed policy: AWSMarketplaceLicenseManagementServiceRolePolicy<a name="security-iam-awsmanpol-awsmarketplacelicensemanagementservicerolepolicy"></a>

You can't attach AWSMarketplaceLicenseManagementServiceRolePolicy to your IAM entities\. This policy is attached to a service\-linked role that allows AWS Marketplace to perform actions on your behalf\. For more information, see [Using service\-linked roles for AWS Marketplace](buyer-using-service-linked-roles.md)\.

This policy grants contributor permissions that allow AWS Marketplace to manage licenses on your behalf\.

**Permissions details**

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AllowLicenseManagerActions",
            "Effect": "Allow",
            "Action": [
                "organizations:DescribeOrganization",
                "license-manager:ListReceivedGrants",
                "license-manager:ListDistributedGrants",
                "license-manager:GetGrant",
                "license-manager:CreateGrant",
                "license-manager:CreateGrantVersion",
                "license-manager:DeleteGrant",
                "license-manager:AcceptGrant"
            ],
            "Resource": [
                "*"
            ]
        }
    ]
}
```

## AWS managed policy: AWSMarketplaceManageSubscriptions<a name="security-iam-awsmanpol-awsmarketplacemanagesubscriptions"></a>

You can attach the `AWSMarketplaceManageSubscriptions` policy to your IAM identities\.

This policy grants contributor permissions that allow subscribing and unsubscribing to AWS Marketplace products\.

**Permissions details**

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "aws-marketplace:ViewSubscriptions",
                "aws-marketplace:Subscribe",
                "aws-marketplace:Unsubscribe"
            ],
            "Effect": "Allow",
            "Resource": "*"
        },
        {
            "Action": [
                "aws-marketplace:CreatePrivateMarketplaceRequests",
                "aws-marketplace:ListPrivateMarketplaceRequests",
                "aws-marketplace:DescribePrivateMarketplaceRequests"
            ],
            "Effect": "Allow",
            "Resource": "*"
        }
    ]
}
```

## AWS managed policy: AWSMarketplaceProcurementSystemAdminFullAccess<a name="security-iam-awsmanpol-awsmarketplaceprocurementsystemadminfullaccess"></a>

You can attach the `AWSMarketplaceProcurementSystemAdminFullAccess` policy to your IAM identities\.

This policy grants admin permissions that allow managing all aspects of an AWS Marketplace eProcurement integration, including listing the accounts in your organization\. For more information about eProcurement integrations, see [Integrating AWS Marketplace with procurement systems](procurement-system-integration.md) \.

**Permissions details**

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:PutProcurementSystemConfiguration",
                "aws-marketplace:DescribeProcurementSystemConfiguration",
                "organizations:Describe*",
                "organizations:List*"
            ],
            "Resource": [
                "*"
            ]
        }
    ]
}
```

## AWS managed policy: AWSMarketplaceRead\-only<a name="security-iam-awsmanpol-awsmarketplaceread-only"></a>

You can attach the `AWSMarketplaceRead-only` policy to your IAM identities\.

This policy grants read\-only permissions that allows viewing products and subscriptions for your account on AWS Marketplace, as well as viewing the Amazon EC2, AWS Identity and Access Management, and Amazon SNS resources in the account\.

**Permissions details**

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Resource": "*",
            "Action": [
                "aws-marketplace:ViewSubscriptions",
                "ec2:DescribeAccountAttributes",
                "ec2:DescribeAddresses",
                "ec2:DescribeImages",
                "ec2:DescribeInstances",
                "ec2:DescribeKeyPairs",
                "ec2:DescribeSecurityGroups",
                "ec2:DescribeSubnets",
                "ec2:DescribeVpcs"
            ],
            "Effect": "Allow"
        },
        {
            "Resource": "*",
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:ListBuilds",
                "aws-marketplace:DescribeBuilds",
                "iam:ListRoles",
                "iam:ListInstanceProfiles",
                "sns:GetTopicAttributes",
                "sns:ListTopics"
            ]
        },
        {
            "Resource": "*",
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:ListPrivateMarketplaceRequests",
                "aws-marketplace:DescribePrivateMarketplaceRequests"
            ]
        }
    ]
}
```

## AWS managed policy: AWSPrivateMarketplaceAdminFullAccess<a name="security-iam-awsmanpol-awsprivatemarketplaceadminfullaccess"></a>

You can attach the `AWSPrivateMarketplaceAdminFullAccess` policy to your IAM identities\.

This policy grants admin permissions that allow full access to manage private marketplaces in your account \(or organization\)\.

**Permissions details**

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:AssociateProductsWithPrivateMarketplace",
                "aws-marketplace:DisassociateProductsFromPrivateMarketplace",
                "aws-marketplace:ListPrivateMarketplaceRequests",
                "aws-marketplace:DescribePrivateMarketplaceRequests"
            ],
            "Resource": [
                "*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:ListEntities",
                "aws-marketplace:DescribeEntity",
                "aws-marketplace:StartChangeSet",
                "aws-marketplace:ListChangeSets",
                "aws-marketplace:DescribeChangeSet",
                "aws-marketplace:CancelChangeSet"
            ],
            "Resource": "*"
        }
    ]
}
```

## AWS managed policy: AWSPrivateMarketplaceRequests<a name="security-iam-awsmanpol-awsprivatemarketplacerequests"></a>

You can attach the `AWSPrivateMarketplaceRequests` policy to your IAM identities\.

This policy grants contributor permissions that allow access to request products be added to your private marketplace, and to view those requests\. These requests must be approved or denied by a private marketplace administrator\.

**Permissions details**

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:CreatePrivateMarketplaceRequests",
                "aws-marketplace:ListPrivateMarketplaceRequests",
                "aws-marketplace:DescribePrivateMarketplaceRequests"
            ],
            "Resource": "*"
        }
    ]
}
```



## AWS Marketplace updates to AWS managed policies<a name="security-iam-awsmanpol-updates"></a>

View details about updates to AWS managed policies for AWS Marketplace since this service began tracking these changes\. For automatic alerts about changes to this page, subscribe to the RSS feed on the AWS Marketplace [Document history](document-history.md) page\.






| Change | Description | Date | 
| --- | --- | --- | 
|  [ AWSPrivateMarketplaceAdminFullAccess](#security-iam-awsmanpol-awsprivatemarketplaceadminfullaccess) – Update to an existing policy  |  AWS Marketplace removed unused permissions in the `AWSPrivateMarketplaceAdminFullAccess` policy\.  | August 27, 2021 | 
|  [ AWSMarketplaceFullAccess](#security-iam-awsmanpol-awsmarketplacefullaccess) – Update to an existing policy  |  AWS Marketplace removed a duplicate `ec2:DescribeAccountAttributes` permission from `AWSMarketplaceFullAccess` policy\.  | July 20, 2021 | 
|  AWS Marketplace started tracking changes  |  AWS Marketplace started tracking changes for its AWS managed policies\.  | April 20, 2021 | 