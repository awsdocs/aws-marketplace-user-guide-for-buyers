# AMI products with contract pricing<a name="buyer-ami-contracts"></a>

Some sellers offer public Amazon Machine Image \(AMI\)\-based software products with a contract pricing model\. In that model, you agree to make a one\-time upfront payment for discrete quantities of licenses to access the software product for a duration of your choice\. You're billed, in advance, through your AWS account\. For example, you might purchase 10 user access licenses and 5 administrative licenses for a year\. You can choose to automatically renew the licenses\.

In addition, some companies offer private AMI\-based software products with a contract pricing model\. A private offer typically has a fixed duration which you can't change\.

You can purchase an AMI \-based software product contract using the product’s detail page on AWS Marketplace\. If this option is available, **AMI with contract pricing** appears for **Delivery Method** on the product’s detail page\. When you make the purchase, you will be directed to the product’s website for account setup and conﬁguration\. The usage charges will then appear on your regular AWS account billing report\.

## Subscribing to an AMI product with contract pricing public offer<a name="sub-public-AMI-contract"></a>

**To subscribe to a public offer AMI\-based product with a contract pricing model**

1. Sign in to AWS Marketplace and find a container\-based software product with a contract pricing model\.

1. On the **Procurement** page, view the **Pricing Information**\.

   You can see the **Units** and the rate for each duration \(in months\)\.

1. Choose **Continue to Subscribe** to start the subscription\. 

   To save this product without subscribing, choose **Save to List**\.

1. Create an agreement by reviewing the pricing information and configuring the terms for the software product\. 

   1. Choose the duration of the contract: **1 month**, **12 months**, **24 months**, or **36 months** 

   1. Under **Renewal Settings**, choose whether to automatically renew the contract\.

   1. Under **Contract options**, choose a quantity for each unit\.

   The total contract price is displayed under **Pricing details\.**

1. After you have made your selections, choose **Create Contract**\.

The **Total contract price** is charged to your AWS account\. A license is generated in AWS License Manager\.

**Note**  
It can take up to 10 minutes for the subscription to process and a license to be generated in your AWS License Manager account for the software product\.

## Subscribing to an AMI product with contract pricing private offer<a name="sub-private-AMI-contract"></a>

**To subscribe to a private offer AMI\-based product with a contract pricing model**

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

**To access the AMI\-based software product**

1. On the AWS Marketplace console, navigate to **View Subscription** and view the license for the software product\. 

1. On the **Procurement** page:

   1. Choose **Manage License** to view, grant access, and track usage of your entitlements in AWS License Manager\.

   1. Choose **Continue to Configuration**\. 

1. On the **Launch** page, review your configuration and choose how you want to launch the software under **Choose Action**\.

1. On the **Choose an Instance Type**, choose an Amazon Elastic Compute Cloud \(Amazon EC2\) instance, and then choose **Next: Configure Instance Details**\.

1. On the **Configure Instance Details** page, for **IAM role,** choose an existing AWS Identity and Access Management \(IAM\) role from your AWS account\. 

   If you don't have an IAM role, choose the **Create new IAM role manually** link and follow the instructions\.
**Note**  
When you purchase a product with contract pricing, a license is created by AWS Marketplace on the AWS account that your software can check using the License Manager API\. You will need an IAM role to launch an instance of the AMI\-based product\.  
The following IAM permissions are required in the IAM policy\.  

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

1. After the instance details are configured, choose **Review and Launch**\.

1. On the **Review Instance Launch** page, select an existing key pair or create a new key pair, and then choose **Launch Instances**\.

   The **Initiating Instance Launches** progress window appears\.

1. After the instance is initiated, go to the EC2 dashboard, and under **Instances**, see that the **Instance state** displays **Running**\.

## Viewing a generated license<a name="view-generated-license"></a>

**To view a generated license**

1. Sign in to to AWS License Manager with your AWS account\.

1. Under **Granted licenses**, view all of your granted licenses\.

1. Search licenses by entering a product SKU, recipient, or status in the **Search** bar\.

1. Choose the **License ID** and view the **License details**\. 

1. You can view the **Issuer** \(AWS/Marketplace\)and the **Entitlements** \(the units that the license grants the right to use, access, or consume an application or resource\)\. 