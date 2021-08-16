# Private marketplaces<a name="private-marketplace"></a>

A private marketplace controls which products users in your AWS account, such as business users and engineering teams, can procure from AWS Marketplace\. It is built on top of AWS Marketplace, and enables your administrators to create and customize curated digital catalogs of approved independent software vendors \(ISVs\) and products that conform to their in\-house policies\. Users in your AWS account can find, buy, and deploy approved products from your private marketplace, and ensure that all available products comply with your organization’s policies and standards\. 

Your private marketplace is shared across your organization\. With [AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/), you can create a series of accounts linked for permissions and payments\. You can create one or more private marketplace experiences that are associated with one or more accounts in your organization, each with its own set of approved products\. Your administrators can also apply company branding to each private marketplace experience with your company or team’s logo, messaging, and color scheme\. 

A private marketplace provides you with a broad catalog of products available in AWS Marketplace to choose from, in addition to fine\-grained control of those products\. 

This section describes using private marketplace as a product purchaser\. For information about managing private marketplaces as an administrator, see [Creating and managing a private marketplace](private-catalog-administration.md)\.

**Notes**  
You can't add [desktop products](buyer-desktop-products.md) to a private marketplace\. 
You can add private products that have been shared with you \(via a [ private offer](https://docs.aws.amazon.com/marketplace/latest/buyerguide/buyer-private-offers.html)\) to a private marketplace\. For more information, see [Subscribing to a private product in a private marketplace ](#subscribing-to-a-private-product-in-a-private-marketplace)\.
In a private marketplace, customers are automatically entitled to any products whose EULAs are governed by the AWS Customer Agreement or other agreement with AWS governing use of AWS services\. Customers are already entitled to these products by default; therefore, they are not included in the list of products that you approved within your private marketplace\. Customers can use AWS Service Catalog to manage the deployment of these products\.

## Viewing product detail pages<a name="product-detail-page-visit"></a>

Users can only subscribe to products you have allowed in the private marketplace that governs the account\. They can browse and see the detail page for any product, but subscription is enabled only for products you have added to your private marketplace\. If a product is not currently in your private marketplace, the user sees a red banner at the top of the page, noting that the product is not approved for procurement in AWS Marketplace\.

If software requests are enabled, users can choose **Create request** on the product details page\. When users choose **Create request**, they submit a request to the administrator to make the product available on your private marketplace\. For more information about this feature, see [Managing user requests](private-catalog-administration.md#manage-user-requests-private-marketplace)\.

## Subscribing to a product in a private marketplace<a name="subscribing-to-a-product-in-a-private-marketplace"></a>

To subscribe to a product in your private marketplace as a user, navigate to the product's details page and choose **Continue**\. This redirects you to the product's subscription page\. On the subscription page, you can make your configuration selections, and then choose **Subscribe**\.

If the product is not approved in your private marketplace, **Subscribe** isn't available\. A red banner at the top of the page indicates that the product is not currently approved for procurement\. If software requests are enabled, you can choose **Create request** to submit a request to your administrator requesting that the product be added to your private marketplace\.

## Subscribing to a private product in a private marketplace<a name="subscribing-to-a-private-product-in-a-private-marketplace"></a>

Some products are not publicly available to browse in AWS Marketplace\. These products can only be seen when you are given a private offer from the seller\. However, you can only subscribe if your private marketplace administrator first adds the product to your private marketplace\. Because of this, the private offer must be extended to both your AWS account and the account that includes your organization's private marketplace administrator\. After the private offer has been extended to both the user account and the administrator's account, the private marketplace administrator can add the product to your private marketplace\. After the product has been approved, you can subscribe to the product like any other private offer\.

## Requesting a product be added to your private marketplace<a name="request-adding-a-product-to-your-private-marketplace"></a>

As a user, you can request that your administrator add a product that is not in your private marketplace\. To make a request, navigate to the product's details page, choose **Create request**, enter a request to your administrator that the product be added to your private marketplace, and then submit your request\. To track your request status, on the left dropdown menu, choose **Your Private Marketplace Requests**\.