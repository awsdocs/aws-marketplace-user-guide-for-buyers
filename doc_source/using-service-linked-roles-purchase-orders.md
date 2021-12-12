# Using roles to work with purchase orders in AWS Marketplace<a name="using-service-linked-roles-purchase-orders"></a>

AWS Marketplace uses AWS Identity and Access Management \(IAM\)[ service\-linked roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html#iam-term-service-linked-role)\. A service\-linked role is a unique type of IAM role that is linked directly to AWS Marketplace\. Service\-linked roles are predefined by AWS Marketplace and include all the permissions that the service requires to call other AWS services on your behalf\. 

A service\-linked role makes setting up AWS Marketplace easier because you don’t have to manually add the necessary permissions\. AWS Marketplace defines the permissions of its service\-linked roles, and unless defined otherwise, only AWS Marketplace can assume its roles\. The defined permissions include the trust policy and the permissions policy, and that permissions policy cannot be attached to any other IAM entity\.

You can delete a service\-linked role only after first deleting their related resources\. This protects your AWS Marketplace resources because you can't inadvertently remove permission to access the resources\.

For information about other services that support service\-linked roles, see [AWS services that work with IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_aws-services-that-work-with-iam.html) and look for the services that have **Yes **in the **Service\-linked roles** column\. Choose a **Yes** with a link to view the service\-linked role documentation for that service\.

## Service\-linked role permissions for AWS Marketplace<a name="service-linked-role-permissions-purchase-orders"></a>

AWS Marketplace uses the service\-linked role named **AWSServiceRoleForMarketplacePurchaseOrders** – this role provides AWS Marketplace permissions to attach purchase order numbers to your AWS Marketplace subscriptions in AWS Billing and Cost Management\.

The **AWSServiceRoleForMarketplacePurchaseOrders** service\-linked role trusts the following services to assume the role:
+ `purchase-orders.marketplace.amazonaws.com`

The role permissions policy named **AWSMarketplacePurchaseOrdersServiceRolePolicy** allows AWS Marketplace to complete the following actions on the specified resources:
+ Action: `"purchase-orders:ViewPurchaseOrders", "purchase-orders:ModifyPurchaseOrders"` on `"*"`

You must configure permissions to allow an IAM entity \(such as a user, group, or role\) to create, edit, or delete a service\-linked role\. For more information, see [Service\-linked role permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html#service-linked-role-permissions) in the *IAM User Guide*\.

## Creating a service\-linked role for AWS Marketplace<a name="create-service-linked-role-purchase-orders"></a>

You don't need to manually create a service\-linked role\. When you set up integrating with AWS Billing and Cost Management, AWS Marketplace creates the service\-linked role for you\. 

**Note**  
Within AWS Organizations, this setting only works in the management account\. You must perform this procedure from the management account\. This sets up the service linked role and purchase order support for all accounts in the organization\.

**To create a service\-linked role**

1. In the [AWS Marketplace console](https://console.aws.amazon.com/marketplace/), sign in to the management account and choose **Settings**\.

1. In the **AWS Billing integration** section, select **Configure integration**\.

1. On the **Create AWS Billing integration** page, select **AWS Marketplace billing management service\-linked role for your organization**, then choose **Create integration**\.

If you delete this service\-linked role, and then need to create it again, you can use the same process to recreate the role in your account\. When you set up integrating with AWS Billing and Cost Management, AWS Marketplace creates the service\-linked role for you again\. 

## Editing a service\-linked role for AWS Marketplace<a name="edit-service-linked-role-purchase-orders"></a>

AWS Marketplace does not allow you to edit the **AWSServiceRoleForMarketplacePurchaseOrders** service\-linked role\. After you create a service\-linked role, you cannot change the name of the role because various entities might reference the role\. However, you can edit the description of the role using IAM\. For more information, see [Editing a service\-linked role](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html#edit-service-linked-role) in the *IAM User Guide*\.

## Deleting a service\-linked role for AWS Marketplace<a name="delete-service-linked-role-purchase-orders"></a>

If you no longer need to use a feature or service that requires a service\-linked role, we recommend that you delete that role\. That way you don’t have an unused entity that is not actively monitored or maintained\. However, you must clean up your service\-linked role before you can manually delete it\.

**Manually deleting the service\-linked role**

Use the IAM console, the AWS CLI, or the AWS API to delete the **AWSServiceRoleForMarketplacePurchaseOrders** service\-linked role\. For more information, see [Deleting a service\-linked role](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html#delete-service-linked-role) in the *IAM User Guide*\.

## Supported Regions for AWS Marketplace service\-linked roles<a name="slr-regions-purchase-orders"></a>

AWS Marketplace supports using service\-linked roles in all of the AWS Regions where the service is available\. For more information, see [AWS Marketplace Regions and Endpoints](https://docs.aws.amazon.com/general/latest/gr/aws-marketplace.html#aws-marketplace_region)\.