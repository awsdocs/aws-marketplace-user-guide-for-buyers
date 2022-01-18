# Setting up procurement system integration<a name="procurement-system-integration-setup"></a>

To configure the integration between AWS Marketplace and your procurement system, you start the process in AWS Marketplace and complete it in the procurement system\. You use the information generated in AWS Marketplace to configure the procurement system punchout\. To complete the configuration, the accounts that you use must meet the following requirements:
+ The AWS account used to complete the AWS Marketplace configuration must be the management account and have the AWS Identity and Access Management \(IAM\) permissions defined in the `AWSMarketplaceProcurementSystemAdminFullAccess` managed policy\.
+  The procurement system account used to complete the configuration must have administration access to set up a contract, supplier, and punchout catalog in the procurement system\.

## Configuring IAM permissions<a name="procurement-system-integration-setup-iam-permissions"></a>

 The following IAM permissions are in the [AWS managed policy: AWSMarketplaceProcurementSystemAdminFullAccess](buyer-security-iam-awsmanpol.md#security-iam-awsmanpol-awsmarketplaceprocurementsystemadminfullaccess) managed policy and are required to configure the integration between AWS Marketplace and a procurement system\. 

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

We recommend that you use IAM managed permissions rather than manually configuring permissions\. Using this approach is less prone to human error, and if the permissions change, the managed policy is updated\. For more information about configuring and using IAM in AWS Marketplace, see [Security on AWS Marketplace](buyer-security.md)\.

## Configuring AWS Marketplace to integrate with Coupa<a name="coupa-integration-setup-awsmp-configuration"></a>

After you have setup your IAM permissions, you are ready to configure AWS Marketplace integration with Coupa\. Navigate to **Manage procurement**\. In the **Manage procurement systems** pane, enter a name and description for the punchout\. You can also switch the integration to test mode so that users can test the integration without creating product subscriptions until you're ready\. To configure the AWS Marketplace portion of the integration, complete the following procedure\. 

**To configure AWS Marketplace for integrating with Coupa**

1.  From [AWS Marketplace Manage Procurement Systems](https://aws.amazon.com/marketplace/eprocurement/overview), under **Procurement systems**, choose **Set up Coupa integration**\. 

1.  On the **Manage Coupa integration** page, under **Account information**, enter the name and description of your integration\. 

1. Make sure that the **Enable redirect** option is on and that **Test mode** is enabled, then select **Save** to complete the integration in the AWS Marketplace system\.

After you have completed the integration in AWS Marketplace, you must go on to setup the integration in Coupa\. You use the information generated on this page to configure the punchout in your Coupa system\. 

The AWS Marketplace configuration defaults to test mode being enabled\. In test mode, subscription requests go to the Coupa backend so you can see the full flow, but a final invoice is not created\. This helps you complete the configuration and enable the punchout in a planned manner\.

**Note**  
You can toggle testing mode on or off, as needed\.  
Don't forget to turn off testing mode when you're finished with your integration\. Otherwise, users in your system will appear to be creating requests, but no software will be purchased\.

Although AWS Marketplace uses cXML for the punchout integration, it uses Coupa Supplier Portal integration to invoice, not cXML invoicing\.

### Configuring Coupa<a name="coupa-integration-setup-coupa-configuration"></a>

 To configure the integration with AWS Marketplace in your Coupa system, copy the information from the **Purchase information** pane of the **Manage Coupa integration** page in AWS Marketplace\. Use this information to complete the steps in the following links that guide you through configuring your Coupa procurement system: 
+  [Coupa Punchout Setup](https://success.coupa.com/Suppliers/For_Customers/Toolkit/Manage_Catalogs/Punchout_Catalogs/Punchout_Setup) 
+  [Configuring a Supplier for cXML Purchase Orders](https://success.coupa.com/Suppliers/For_Customers/Toolkit/Document_Exchange/cXML/Configuring_a_Supplier_for_cXML_Purchase_Orders) 

**Note**  
For information about UNSPSC codes used by AWS Marketplace, see [UNSPSC codes used by AWS Marketplace](#procurement-integration-setup-unspsc-codes) \.

## Configuring AWS Marketplace to integrate with SAP Ariba<a name="ariba-integration-setup-awsmp-configuration"></a>

 To configure AWS Marketplace to integrate with Ariba, you must work with the AWS Marketplace operations team to create a Level 1 punchout\. For more information about SAP Ariba punchout, see [Introduction to SAP Ariba PunchOut](https://blogs.sap.com/2019/11/27/introduction-to-sap-ariba-punchout/) on the *SAP Community* website\.

Gather the following information in preparation for configuring the setup:
+ Your AWS account ID\. If your AWS account is part of an AWS organization, then you also need the management account ID\.
+ The Ariba network ID \(ANID\) for your SAP Ariba system\.
**Note**  
For information about ANIDs in Ariba, and answers to other questions about Ariba see the [ Ariba Network for Suppliers: Frequently Asked Questions](https://www.ariba.com/ariba-network/ariba-network-for-suppliers/accounts-and-pricing/ariba-network-faq) page on the *SAP Ariba* website\.

**To configure AWS Marketplace for integrating with Ariba**

1.  From [AWS Marketplace Manage Procurement Systems](https://aws.amazon.com/marketplace/eprocurement/overview), under **Procurement systems**, choose **Set up Ariba integration**\. 

1.  On the **Manage SAP Ariba integration** page, under **Account information**, enter the name and description of your integration, as well as the **SAP Ariba Network ID** \(ANID\) for your Ariba system\.

1. Make sure that **Test mode** is enabled, then select **Save** to save your AWS Marketplace integration settings\.

1. [Contact us](https://aws.amazon.com/marketplace/help/contact-us) to start the process of creating your SAP Ariba integration\. Include the above information\. AWS Marketplace sends you instructions for setting up and testing your Ariba integration\.

**Note**  
You need to have administrator access to your SAP Ariba system to create the *Supplier Relationship* with AWS Marketplace\.

Following the instructions and configuration settings from the AWS Marketplace team, you create the integration in your SAP Ariba test environment, with AWS Marketplace running in *test mode*\. In the test environment, subscription requests go to the Ariba backend so you can see the full flow including approvals, without creating a subscription in AWS Marketplace, and no invoice is generated\. This approach enables testing the configuration prior to enabling the punchout in production\. After your testing is complete and you are ready to move to production, [contact us](https://aws.amazon.com/marketplace/help/contact-us) to setup the account in the production environment\.

**Note**  
Don't forget to move to production when you're finished with testing your integration\. Otherwise, users in your system will believe that they're creating requests, but no software will be purchased\.

When your testing is complete, and you have worked with the AWS Marketplace team to turn off test mode, your integration is complete\.

For more information about configuring SAP Ariba, see the following topics from SAP Ariba:
+ [ SAP Ariba PunchOut](https://www.ariba.com/ariba-network/ariba-network-for-suppliers/selling-on-ariba-network/catalog-management/sap-ariba-punchout) on the *SAP Ariba* website
+ [Introduction to SAP Ariba PunchOut](https://blogs.sap.com/2019/11/27/introduction-to-sap-ariba-punchout/) on the *SAP Community* website

**Note**  
For information about UNSPSC codes used by AWS Marketplace, see [UNSPSC codes used by AWS Marketplace](#procurement-integration-setup-unspsc-codes) \.

## UNSPSC codes used by AWS Marketplace<a name="procurement-integration-setup-unspsc-codes"></a>

AWS Marketplace includes the following United Nations Standard Products and Services Code \(UNSPSC\) codes for the software listings sent back to the procurement system cart:
+  Software as a service \(SaaS\) products: 81162000 
+  Application server products: 43232701 
+  Other software, such as containers, AWS WAF rules, and machine learning \(ML\) algorithms: 43230000 

## Disabling procurement system integration<a name="procurement-integration-disabling"></a>

To disable integration with either Coupa or SAP Ariba, you must remove the punchout integration from within the procurement system\. To do this, disable the auto\-redirect functionality for AWS Marketplace from within either Coupa or Ariba\. This disables the integration, but maintains the settings and allows it to be re\-enabled easily\.

If you need to completely remove the integration setup on the AWS Marketplace side, you must [contact us](https://aws.amazon.com/marketplace/help/contact-us)\.