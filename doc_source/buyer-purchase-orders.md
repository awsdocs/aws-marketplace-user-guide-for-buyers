# Specifying purchase order numbers for SaaS contract products<a name="buyer-purchase-orders"></a>

When you purchase software as a service \(SaaS\) contract products in AWS Marketplace, you can specify a purchase order number during the checkout process\. This purchase order number is included on the invoice for your SaaS contract purchase and is included in the [ Purchase Orders dashboard in the AWS Billing](http://aws.amazon.com/aws-cost-management/aws-purchase-order-management) console\.

**Prerequisites**
+ To use purchase order support for SaaS contract products, you must first give AWS Marketplace access to make changes to AWS Billing and Cost Management on your behalf\. For information about how to give AWS Marketplace these permissions, see [Creating a service\-linked role for AWS Marketplace](using-service-linked-roles-purchase-orders.md#create-service-linked-role-purchase-orders)\. For AWS accounts that are part of AWS Organizations, this integration must happen from the management account, and the purchase order support is for all accounts in the organization\.
+ Users who need to add the purchase order number to a purchase must have the `aws-marketplace:Subscribe` permission, for example, by using the [AWS managed policy: AWSMarketplaceManageSubscriptions](buyer-security-iam-awsmanpol.md#security-iam-awsmanpol-awsmarketplacemanagesubscriptions)\.

**To specify a purchase order for a SaaS contract product**

1. Find and prepare to purchase a SaaS product from AWS Marketplace as you normally would\.

1. During the purchase flow, on the **Configure your software subscription** page, in the **Purchase order** box, choose **Add purchase order number**\.

1. Enter your purchase order number in the **Purchase order number** field\. 

   Your purchase order number is the number or text that you use to track your purchase order in your system\. It is usually issued by an internal system or process\. It can be up to 200 characters in length\.

Details about a purchase order, including all AWS Marketplace purchases that were given that same purchase order number, can be found in the [ Purchase Orders dashboard in the Billing and Cost Management](http://aws.amazon.com/aws-cost-management/aws-purchase-order-management) console\. Each SaaS contract product with that purchase order number is shown as a separate line item in the purchase order details in the Purchase Orders dashboard

## Troubleshooting purchase orders<a name="buyer-purchase-order-troubleshooting"></a>

The information in the following table can help you troubleshoot issues with purchase orders, or understand what happens in different scenarios\.


| Scenario | Details | 
| --- | --- | 
| Purchase order does not exist | AWS Marketplace creates a new purchase order for you\. The new purchase order has default information, with no contact information\.  | 
| Missing purchase order notifications | Purchase orders without contact information \(including the purchase orders created by AWS Marketplace\) do not receive email notifications\. You can add contact information to a purchase order in the [ Purchase Orders dashboard in the Billing and Cost Management](http://aws.amazon.com/aws-cost-management/aws-purchase-order-management) console\. | 
| Incorrect purchase order number added | If you enter an incorrect purchase order number and need to update it, contact AWS Support to update the purchase order number\. | 
|  Subscribing account moves to a different organization  |  For purchase orders to work in the new organization, the integration must be completed in the new organization\. If integration has been completed, and purchase order support is working in the new organization, then when the subscribing account moves between organizations, new invoices show the purchase order number in the new organization \(and a new purchase order is created, if necessary\)\.  | 
| Purchase order option not available when checking out | Purchase order integration is only available for SaaS products with contract\-pricing\. | 
|   Contracts with pay as you go  |   The invoice for the contract shows the purchase order number, but the invoice for consumption \(pay as you go\) does not show the purchase order number\. Pay as you go does not support adding purchase order numbers\.  | 
|   Suspended purchase order  |   When a purchase order number is provided, and the purchase order is marked as suspended in the Purchase Orders dashboard in the Billing and Cost Management console, the new line item is added to the purchase order, but the invoice does not include the purchase order\. The billing admin for the AWS account needs to make the purchase order active, and contact AWS Support to regenerate the invoice with the active purchase order\.  | 
|   Expired purchase order  |   When a purchase order number is provided, and the purchase order is expired, the new line item is created and the purchase order is marked as active\. The line item's end date is used as the new purchase order expiration date\.  | 
|   Balance tracking  |   Balance tracking is not enabled for AWS Marketplace line items\.  | 
|   Procurement system integration  |  The purchase order provided by an integrated procurement system is shown on invoices\.  | 
|   Flexible payment schedule \- initial purchase  |   A contract that has specific dates for invoicing \(flexible payment schedule\) generates an initial line item in the purchase order for zero dollars\. Additional line items with applicable prices are created for each invoice\.  | 
| Flexible payment schedule \- multiple purchase orders | If you need your individual payments for a flexible payment schedule to show up with different purchase orders, contact AWS Support to change the purchase order number on future invoices\. | 