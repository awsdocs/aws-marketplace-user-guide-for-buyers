# Sharing subscriptions in an organization<a name="organizations-sharing"></a>

When you subscribe to products in AWS Marketplace, an agreement is created that grants you license to use those products\. If your AWS account is a member of an organization, you can share that license for AMI, container, and machine learning products with the other accounts in that organization\. You must set up license support in AWS Marketplace, and then share from within AWS License Manager\.

**Note**  
For more information about AWS Organizations, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/)\.  
For more information about sharing licenses with your organization in AWS License Manager, see [ Granted licenses](https://docs.aws.amazon.com/license-manager/latest/userguide/granted-licenses.html) in the *AWS License Manager User Guide*\.

The following topics outline the process of sharing the licenses across accounts\.

**Topics**
+ [Prerequisites for license sharing](#license-sharing-prereqs)
+ [Viewing and sharing your licenses](#view-share-licenses)

## Prerequisites for license sharing<a name="license-sharing-prereqs"></a>

Before you can share licenses in AWS Marketplace you must set up license sharing for your organization\. Complete the following tasks to set up license sharing for your organization:
+ Give AWS Marketplace permission to manage licenses on your behalf so that it can create the associated license grants when you purchase or share your licenses\. For more information, see [Service\-linked roles for AWS Marketplace](buyer-using-service-linked-roles.md)\.
+ Set up AWS License Manager for first use\. For more information, see [ Getting started with AWS License Manager](https://docs.aws.amazon.com/license-manager/latest/userguide/getting-started.html) in the *AWS License Manager User Guide*\.

## Viewing and sharing your licenses<a name="view-share-licenses"></a>

AWS Marketplace automatically creates licenses for AMI, container, machine learning, and data products that you purchase\. You can share those licenses with other accounts in your organization\.

You manage and share licenses using AWS License Manager\. However, you can use AWS Marketplace to view the licenses for products that you purchased from within AWS Marketplace\.

**To view licenses for your subscribed products**

1. In [AWS Marketplace](https://aws.amazon.com/marketplace/), sign in and choose **Manage Subscriptions**\.

1. You can view all licenses or view the license for a specific subscription\.
   + To view all licenses

     1. From the **Actions** menu, select **View Licenses** to view all AWS Marketplace managed licenses in the License Manager console\.
   + To view licenses for a single subscription

     1. Choose the card of the product that you want to view to go to its product details page\.

     1. From the **Actions** menu, select **View License** to view the license for that product in the License Manager console\.

**Note**  
Subscriptions in AWS Marketplace have an **Access level** shown in the product details\. Products with an **Agreement** level have a license that you can use and share with other accounts in your organization\. Products with an **Entitlement** level are licenses that have been shared with your account—you can use these products, but you can't share them\.  
Only AMI, container, and machine learning products will have licences that can be shared\.

From License Manager, you can share your license with other accounts in your organization\. For more details about using License Manager with AWS managed licenses, see the [ Granted licenses](https://docs.aws.amazon.com/license-manager/latest/userguide/granted-licenses.html) and [Seller issued licenses](https://docs.aws.amazon.com/license-manager/latest/userguide/granted-licenses.html) topics in the *AWS License Manager User Guide*\.

**Note**  
For products that are restricted to specific regions, an account you share your license with will only be able to activate the license if the account is within an allowed region\.