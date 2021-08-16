# Controlling access to AWS Marketplace subscriptions<a name="buyer-iam-users-groups-policies"></a>

The recommended way to let other people in your organization manage subscriptions is to use AWS Identity and Access Management \(IAM\) to create users and groups\. For example, if John should be allowed only to view your subscriptions, you can create an IAM user for him and add his IAM user to the read\-only group\. If John's role in your organization changes or he leaves the company, you can change the group that his IAM user belongs to, or you can change his user's settings in IAM\. 

**Important**  
All of your users work on the same AWS Marketplace account\. Any change that a user makes to manage a software subscription is global and applies to all of your users for that subscription\. 

## Creating users<a name="buyer-creating-iam-users-for-marketplace"></a>

 To allow people in your company to manage subscriptions, we recommend that you create an IAM user for each person\. For more information, see [IAM Users](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction_identity-management.html#intro-identity-users) in the *IAM User Guide*\. We also recommend you create a user name and password for yourself, even though you are the AWS account owner\. It is a recommended best practice for everyone to work in AWS Marketplace as an IAM user, even the account owner\. To learn how to create an IAM user for yourself that has administrative permissions, see [Creating Your First IAM Admin User and Group](https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started_create-admin-group.html)\. For more information about recommended practices for using IAM, see [IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)\. 

## Creating groups for AWS Marketplace access and adding users to the groups<a name="buyer-creating-iam-groups"></a>

**To create groups for assigning AWS Marketplace permissions**

1. Open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the left navigation pane, choose **Groups** and then choose **Create New Group**\. 

1. For **Group Name**, enter a name for the group, such as *MarketplaceReadOnly* or *MarketplaceFullAccess*, and choose **Next Step**\.

1. On the **Attach Policy** page, select the check box next to one of the following policies: 
   + To allow permissions only to view subscriptions \(but not change them\), choose **AWS MarketplaceRead\-only**
   + To allow permissions to subscribe and unsubscribe, choose **AWSMarketplaceManageSubscriptions**
   + To allow complete control of your subscriptions, choose **AWSMarketplaceFullAccess**

1. Choose **Next Step**, and then choose **Create Group**\.

**To add users to the groups you just created**

1. In the list of groups, choose the name of the group\. 

1. For **Users**, choose **Add Users to Group**\. 

1. Select the users to add to the group, and then choose **Add Users**\.

Repeat the preceding steps to create more groups with different permissions and assign users to those groups\.

You're not limited to the permissions in the AWS managed policies that are described here\. You can use IAM to create policies with custom permissions and then add those policies to IAM groups\. For more information, see [Managing IAM Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-using.html#create-managed-policy-console) and [Attaching a Policy to an IAM Group](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups_manage_attach-policy.html) in the *IAM User Guide*\. 

## AWS managed policies for AWS Marketplace<a name="buyer-iam-builtin-policies"></a>

 After creating users, we recommend that you create groups and apply AWS managed policies to provide basic AWS Marketplace permissions\. Then, for any unique scenarios, you can create your own policies and apply them to the groups with the specific requirements for your scenario\. The following basic AWS Marketplace managed policies are available to you to control who has which permissions:
+ `AWSMarketplaceRead-only`
+ `AWSMarketplaceManageSubscriptions`
+ `AWSPrivateMarketplaceRequests`
+ `AWSPrivateMarketplaceAdminFullAccess`
+ `AWSMarketplaceFullAccess`

AWS Marketplace also provides specialized managed policies for specific scenarios\. For a full list of AWS managed policies for AWS Marketplace buyers, as well as descriptions of what permissions they provide, see [AWS managed policies for AWS Marketplace buyers](buyer-security-iam-awsmanpol.md)\.

## Permissions for working with License Manager<a name="buyer-iam-permissions-for-license-manager"></a>

AWS Marketplace integrates with AWS License Manager to manage and share licenses for products that you subscribe to between accounts in your organization\. To view the full details of your subscriptions in AWS Marketplace, a user must be able to list license information from AWS License Manager\.

To make sure that your users have the permissions they need to see all the data about their AWS Marketplace products and subscriptions, add the following permission:
+ license\-manager:ListReceivedLicenses

For more information about setting permissions, see [Managing IAM Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage.html) in the *IAM User Guide*\.

## Additional resources<a name="buyer-iam-permissions-for-more-information"></a>

For more information about managing IAM users and groups, see [Identities \(Users, Groups, and Roles\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html) in the *IAM User Guide*\. 

For more information about managing IAM permissions and policies, see [Controlling Access Using Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_permissions.html) in the *IAM User Guide*\. 

For more information about managing IAM permissions and policies for data products in AWS Data Exchange, see [Identity and Access Management in AWS Data Exchange](https://docs.aws.amazon.com/data-exchange/latest/userguide/auth-access.html) in the *AWS Data Exchange User Guide*\.