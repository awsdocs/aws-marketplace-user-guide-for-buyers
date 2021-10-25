# Service\-linked roles for AWS Marketplace<a name="buyer-using-service-linked-roles"></a>

AWS Marketplace uses AWS Identity and Access Management \(IAM\) [ service\-linked roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html#iam-term-service-linked-role)\. A service\-linked role is a unique type of IAM role that is linked directly to AWS Marketplace\. Service\-linked roles are predefined by AWS Marketplace and include all the permissions that the service requires to call other AWS services on your behalf\.

A service\-linked role makes setting up AWS Marketplace easier because you don't have to add the necessary permissions manually\. AWS Marketplace defines the permissions of its service\-linked roles, and unless defined otherwise, only AWS Marketplace can assume its roles\. The defined permissions include the trust policy and the permissions policy\. That permissions policy can't be attached to any other IAM entity\.

To share your AWS Marketplace subscriptions to other accounts in your AWS organization with AWS License Manager, you must give AWS Marketplace permissions for each account you want to share with\. Do this by using the **AWSServiceRoleForMarketplaceLicenseManagement** role\. See [Creating a service\-linked role for AWS Marketplace](#buyer-creating-service-linked-role) for more details\.

For information about other services that support service\-linked roles, see [AWS services that work with IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_aws-services-that-work-with-iam.html), and look for the services with **Yes ** in the **Service\-linked roles** column\. Choose a **Yes ** with a link to view the service\-linked role documentation for that service\.

## Service\-linked role permissions for AWS Marketplace<a name="buyer-service-linked-role-permissions"></a>

AWS Marketplace uses the service\-linked role named ** AWSServiceRoleForMarketplaceLicenseManagement**\. This role provides AWS Marketplace with permissions to create and manage licenses in AWS License Manager for the products that you subscribe to in AWS Marketplace\.

This service\-linked role trusts the following service to perform actions in License Manager on your behalf:
+ `license-management.marketplace.amazonaws.com`

The role permissions policy allows AWS Marketplace to complete the following actions on the specified resources:
+ Actions: 
  + `"organizations:DescribeOrganization"`
  + `"license-manager:ListReceivedGrants"`
  + `"license-manager:ListDistributedGrants"`
  + `"license-manager:GetGrant"`
  + `"license-manager:CreateGrant"`
  + `"license-manager:CreateGrantVersion"`
  + `"license-manager:DeleteGrant"`
  + `"license-manager:AcceptGrant"`
+ Resources:
  + All resources \(`"*"`\)

You must configure permissions to allow an IAM entity \(such as a user, group, or role\) to create, edit, or delete a service\-linked role\. For more information, see [ Service\-linked role permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html#service-linked-role-permissions) in the *IAM User Guide*\.

## Creating a service\-linked role for AWS Marketplace<a name="buyer-creating-service-linked-role"></a>

AWS Marketplace creates the service\-linked role for you when you setup integration with AWS License Manager\.

 You can specify that AWS Marketplace create the service\-linked role for all accounts in your organization at once, or you can create the service\-linked role for one account at a time\. The option to create service\-linked roles across all accounts will only be available if your organization has **All features** enabled\. For more details, see [ Enabling all features in your organization](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_org_support-all-features.html) in the *AWS Organizations User Guide*\.

**To create service\-linked roles across all accounts**

1. In [AWS Marketplace console](https://console.aws.amazon.com/marketplace/), sign in and choose **Settings**\.

1. In the **AWS Organizations integration** section, select **Create integration**\.

1. On the **Create AWS Organizations integration** page, select **Enable trusted access across your organization**, then choose **Create integration**\.
**Note**  
This setting enables trust within AWS Organizations\. As a result, in addition to the current action, future accounts that are added to the organization will have the service\-linked role added automatically\.

**To create service\-linked roles for the current account**

1. In [AWS Marketplace console](https://console.aws.amazon.com/marketplace/), sign in and choose **Settings**\.

1. In the **AWS Organizations integration** section, select **Create integration**\.

1. On the **Create AWS Organizations integration** page, select **AWS Marketplace license management service\-linked role for this Account**, then choose **Create integration** \.

**Important**  
If you choose to create the service\-linked role only for the current account, it does not enable trusted access across your organization\. You must repeat these steps for each account that wants to share \(giving or receiving\) licenses in AWS Marketplace\. This includes accounts that are added to the organization in the future\.

## Editing a service\-linked role for AWS Marketplace<a name="buyer-editing-service-linked-role"></a>

AWS Marketplace doesn't allow you to edit the service\-linked role\. After you create a service\-linked role, you cannot change the name of the role because various entities might reference the role\. However, you can edit the description of the role using IAM\. For more information, see [ Editing a service\-linked role](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html#edit-service-linked-role) in the *IAM User Guide*\.

## Deleting a Service\-Linked Role for AWS Marketplace<a name="buyer-delete-service-linked-role"></a>

If you no longer need to use a feature or service that requires a service\-linked role, we recommend that you delete that role\. That way you don’t have an unused entity that is not actively monitored or maintained\. However, you must clean up the resources for your service\-linked role before you can manually delete it\.

**Note**  
If the AWS Marketplace service is using the role when you try to delete the resources, then the deletion might fail\. If that happens, wait for a few minutes and try the operation again\.

**To manually delete the service\-linked role using IAM**

Use the IAM console, the AWS CLI, or the AWS API to delete the AWSServiceRoleForMarketplaceLicenseManagement service\-linked role\. For more information, see [ Deleting a Service\-Linked Role](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html#delete-service-linked-role) in the *IAM User Guide *\.