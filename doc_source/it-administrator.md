# Creating a private marketplace administrator<a name="it-administrator"></a>

You can create an administrators group to manage your company’s [private marketplace](private-marketplace.md) settings\. After the first private marketplace experience is created for your organization, administrators for the private marketplace can perform many tasks including the following: 
+ View and create experiences and account groups\.
+ Add products to private marketplace experiences\.
+ Remove products from private marketplace experiences\.
+ Configure the user interface of private marketplace experiences\.
+ Enable and disable private marketplace experiences\.
+ Call the AWS Marketplace Catalog API to manage private marketplace experiences programmatically\.

To create multiple private marketplace administrators where each administrator is limited to a subset of tasks, see [Creating custom policies for private marketplace administrators](creating-custom-policies-for-private-marketplace-admin.md)\.

**Note**  
Creating the first private marketplace experience also enables private marketplaces in your organization\. This is a one\-time action\. For accounts that are part of an organization, the initial experience creation must happen from the management account\. For more information, see [Creating a private marketplace experience](private-catalog-administration.md#create-your-private-marketplace)\. 

You grant AWS Identity and Access Management \(IAM\) permissions to administer your private marketplace by attaching the [AWS managed policy: AWSPrivateMarketplaceAdminFullAccess](buyer-security-iam-awsmanpol.md#security-iam-awsmanpol-awsprivatemarketplaceadminfullaccess) to an IAM user, group, or role\. We recommend using a group or role\. For more information about how to attach the policy, see [Attaching a policy to an IAM user group](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups_manage_attach-policy) in the *IAM User Guide*\.

For more information about the permissions in the `AWSPrivateMarketplaceAdminFullAccess` policy, see [AWS managed policy: AWSPrivateMarketplaceAdminFullAccess](buyer-security-iam-awsmanpol.md#security-iam-awsmanpol-awsprivatemarketplaceadminfullaccess)\. To learn about other policies for use in AWS Marketplace, sign in to the AWS Management Console, and go to the [IAM policies page](https://console.aws.amazon.com/iam/home?#/policies)\. In the search box, enter **Marketplace** to find all of the policies that are associated with AWS Marketplace\.