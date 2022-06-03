# Container products with contract pricing<a name="buyer-container-contracts"></a>

Some sellers offer public container\-based software products with a contract pricing model, in which you agree to make a one\-time upfront payment for discrete quantities of licenses to access the software product for a duration of your choice, have are billed, in advance, through your AWS account\. 

**Example of purchasing different types of licenses in different quantities**  
For example, you might purchase 10 user access licenses and 5 administrative licenses for a year\. You can choose to automatically renew the licenses\.

In addition, some companies offer private container\-based software products with a contract pricing model\. A private offer typically has a fixed duration that you can't change\.

You can purchase a container\-based software product contract using the product’s detail page on AWS Marketplace\. If this option is available, **AMI with contract pricing** appears for **Delivery Method** on the product’s detail page\. When you make the purchase, you will be directed to the product’s website for account setup and conﬁguration\. The usage charges will then appear on your regular AWS account billing report\.

## Subscribing to a container product with contract pricing public offer<a name="sub-public-container-contract"></a>

**To subscribe to a public offer container\-based product with a contract pricing model**

1. Sign in to AWS Marketplace and find a container\-based software product with a contract pricing model\.

1. On the **Procurement** page, view the **Pricing Information**\.

   You can see the **Units** and the rate against each duration \(in months\)\.

1. Choose **Continue to Subscribe** to start the subscription\. 

   To save this product without subscribing, choose **Save to List**\.

1. Create an agreement by reviewing the pricing information and configuring the terms for the software product\. 

   1. Choose the duration of the contract: **1 month**, **12 months**, **24 months**, or **36 months** 

   1. Under **Renewal Settings**, choose whether to automatically renew the contract\.

   1. Under **Contract options**, choose a quantity for each unit\.

   The total contract price is displayed under **Pricing details\.**

1. After you have made your selections, choose **Create Contract**\.

The **Total contract price** is charged to your AWS account and a license is generated in AWS License Manager\.

**Note**  
It can take up to 10 minutes for the subscription to process and a license to be generated in your License Manager account for the software product\.

## Subscribing to a container product with contract pricing private offer<a name="sub-private-container-contract"></a>

**To subscribe to a private offer container\-based product with a contract pricing model**

1. Sign in to AWS Marketplace with your Buyer account\.

1. View the private offer\. 

1. On the **Procurement** page, view the **Pricing Information**\.

    You can see the **Units** and the rate for each duration \(in months\)\. 

1. Choose **Continue to Subscribe** to start the subscription\. 

1. Create an agreement by reviewing the pricing information and configuring the terms for the software product\. 

   The duration of the contract is already set by the Seller and can't be modified\. 

1. Under **Contract options**, choose a quantity for each unit\.

1. View the total contract price under **Pricing details**\.

   You can also see the public offer by choosing **View Offer** under **Other Available Offers**\.

1. After you have made your selections, choose **Create Contract**\.

**Note**  
It can take up to 10 minutes for the subscription to process and a license to be generated in your AWS License Manager account for the software product\.

## Accessing the software<a name="access-software"></a>

**To access the container\-based software product**

1. On the AWS Marketplace console, navigate to **View Subscription** and view the license for the software product\. 

1. On the **Procurement** page:

   1. Choose **Manage License** to view, grant access, and track usage of your entitlements in AWS License Manager\.

   1. Choose **Continue to Configuration**\. 

1. On the **Launch** page, view the container image details and follow the provided directions\.

   While creating an Amazon Elastic Container Service \(Amazon ECS\) cluster, you need to add the following AWS Identity and Access Management \(IAM\) permissions to your IAM policy\.

   ```
   {
      "Version":"2012-10-17",
      "Statement":[
         {
            "Sid":"VisualEditorO",
            "Effect":"Allow",
            "Action":[
               "license-manager:CheckoutLicense",
               "license-manager:GetLicense",
               "license-manager:CheckInLicense",
               "license-manager:ExtendLicenseConsumption",
               "license-manager:ListReceivedLicenses"
            ],
            "Resource":"*"
         }
      ]
   }
   ```

## Viewing a generated license<a name="view-generated-license"></a>

**To view a generated license**

1. Sign in to AWS License Manager with your AWS account\.

1. Under **Granted licenses**, view all of your granted licenses\.

1. Search licenses by entering a product SKU, recipient, or status in the **Search** bar\.

1. Choose the **License ID** and view the **License details**\. 

1. You can view the **Issuer** \(AWS/Marketplace\) and the **Entitlements** \(the units that the license grants the right to use, access, or consume and application or resource\)\. 

## Modifying an existing contract<a name="modify-existing-contract"></a>

If they have an existing upfront commitment for a Container product, AWS Marketplace buyers can modify some aspects of a contract\. A Container contract is supported through contract terms based offers as opposed to hourly or annual flexible consumption pricing \(FCP\) offers\. This feature is available only to applications that are integrated with AWS License Manager\. Buyers can purchase additional licenses within the entitlement of the same offer in the current contract\. However, buyers can't reduce the entitlement counts purchased in the contract\. Buyers can also cancel the automatic subscription renewal if the option is enabled by the Seller\. 

**Note**  
A flexible payment schedule \(FPS\) contract offer can't be modified\. There are no entitlement changes available to the buyer for an FPS purchased contract\. An entitlement is a right to use, access, or consume an application or resource\. FPS offers are not changeable\.

**Manage your subscription**

1. On the AWS Marketplace console, navigate to **View Subscription** and view the license for the software product\. 

1. On the **Procurement** page, select **Manage License**\.

1. From the list, select **View Terms**\.

1. In the Contract options section, increase your entitlements using the arrows\. You cannot reduce the entitlement counts below the entitelements purchased\. 

1. The contract details and total price displays in the **Pricing details** section\.



**To cancel your automatic subscription renewal**

1. On the AWS Marketplace console, navigate to **View Subscription** and view the license for the software product\. 

1. On the **Procurement** page, select **Manage License**\.

1. On the **Subscription** page, locate the **Renewal Settings** section\.

1. Ensure you understand the terms and conditions with cancellation\.

1. Select the checkbox to cancel the automatic renewal option\. 