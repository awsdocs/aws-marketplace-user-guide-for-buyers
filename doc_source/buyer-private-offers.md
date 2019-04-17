# Private Offers<a name="buyer-private-offers"></a>

 The AWS Marketplace seller private offer feature enables you to receive product pricing from a vendor that isn't publicly available\. You negotiate pricing and terms with the seller, and the seller creates a private offer for the AWS account that you designate\. You accept the private offer and start receiving the negotiated price and terms of use\. 

Each private offer has pricing and licensing terms specifically offered to your account\. The seller of the product extends a private offer to you, and the offer has a set expiration date\. If you don't accept the private offer by the expiration date, depending on the type of product the private offer is for, you're either automatically moved to the product's public offer or no longer subscribed to the product\. 

If you're using the consolidated billing feature in AWS Organizations, we recommend that the account that you designate is your master account\. However, private offers can be made to member accounts, and any member account can accept an offer to their account or to the master account\. For more information on consolidated billing, see [Consolidated Billing for Organizations](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/consolidated-billing.html) in the *AWS Billing and Cost Management User Guide*\. 

## Product Types Eligible for Private Offers<a name="buyer-private-offers-types"></a>

You can get private offers for the following product types\.


| Offer Type | Description | 
| --- | --- | 
|  SaaS contract  |  With a SaaS contract, you commit to upfront payment for your expected usage of a SaaS product\. Contract durations are 1\-month, 1\-year, 2\-year, or 3\-year terms\. You're billed in advance for the use of the product software\.  | 
|  SaaS contract with a flexible payment schedule  |  Same as a SaaS contract, but with a custom payment schedule where payments can be spread over up to 3 years\.  | 
|  SaaS contract with pay\-as\-you\-go pricing for additional usage  |  Same as a SaaS contract, but with negotiated pricing for usage beyond what you negotiated in your contract\.  | 
|  SaaS subscription  |  With a SaaS subscription, you agree to a price for use of a product\. The independent software vendor \(ISV\) tracks and reports your usage to AWS Marketplace, and you're billed for what you use\.   | 
|  AMI hourly  |  With AMI hourly, you negotiate an hourly rate for using an AMI, rounded up to the nearest hour\.   | 
|  AMI annual  |  With AMI annual, you negotiate an hourly price for using the AMI\. The price that you negotiate is effective for 1 year\.  | 
|  AMI Bring Your Own License model \(BYOL\)  |  With AMI BYOL, you can negotiate a price for using an AMI and use software licenses that you already own\. This type of private offer requires that you work with the ISV or a channel partner to sign a custom transaction request \(CTF\) form to agree to pricing, terms, and payment schedule\. The form allows AWS Marketplace to subscribe to the BYOL AMI product on your behalf\.   | 

## Preparing to Accept a Private Offer<a name="buyer-private-offers-prerequsite-steps"></a>

A typical private offer is negotiated for the duration of 1 year, and you pay the entire amount of the offer when you accept it\. Before you accept a private offer, verify the billing structure for your company, your method of payment for AWS billing, and your tax settings\.

### Verifying Your AWS Billing and Cost Management Preferences<a name="buyer-private-offers-prerequsite-steps-billing"></a>

Billing and Cost Management is the service that you use to pay your AWS bill, monitor your usage, and budget your costs\. You can use the consolidated billing feature in AWS Organizations to consolidate billing and payment for multiple accounts or multiple Amazon Internet Services Pvt\. Ltd \(AISPL\) accounts\. Every organization in AWS Organizations has a master account that pays the charges of all the member accounts\. The master account is called a payer account, and the member account is called a linked account\. Before negotiating a private offer, verify how your company pays their AWS bill and which account the private offer is made to\. 

### Verifying Your Payment Method<a name="buyer-private-offers-prerequsite-steps-payment-method"></a>

Before accepting a private offer, verify that your payment method supports paying the entire cost of the private offer\. To verify your payment method, open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

**Note**  
If the private offer is a SaaS contract with a flexible payment schedule, you must have invoicing in place before you accept the offer\.

### Verifying Your Tax Settings<a name="buyer-private-offers-prerequsite-steps-tax-settings"></a>

If your company qualifies for a tax exemption, verify your tax settings\. To view or modify your tax settings, sign in to the AWS Management Console and, in your account settings, view the tax settings\. For more information on tax registration, see [How do I add or update my tax registration number or business legal address for my AWS account?](https://aws.amazon.com/premiumsupport/knowledge-center/update-tax-registration-number/)\.

## Viewing and Subscribing to a Private Offer<a name="buyer-private-offers-subscribing"></a>

The steps required to accept a private offer vary, depending on the product type, delivery method, and payment schedule of your private offer\. With all private offers, you view and accept the offer by logging in to AWS Marketplace and navigating to the offer page for the product\. To view the offer page, you can either:
+ **Use the link the seller provided** – The seller might have sent you a link that takes you directly to the private offer\. If so, use that link to directly access the private offer\.
+ **Navigate to the product page** – Sign in to [AWS Marketplace](https://aws.amazon.com/marketplace) and navigate to the product page for the product\. During the subscription process, you see a banner at the top of the page showing the private offer, offer ID, and expiration for the offer\. If you have more than one private offer for that product, each offer appears under **Offer name**\.