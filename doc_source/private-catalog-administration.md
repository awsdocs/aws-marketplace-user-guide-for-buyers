# Creating and managing a private marketplace<a name="private-catalog-administration"></a>

 To create and manage a private marketplace, you must have the AWS Identity and Access Management \(IAM\) permissions in the AWSPrivateMarketplaceAdminFullAccess IAM policy\. For more information about applying this policy to IAM users, groups, and roles, see [Creating a private marketplace administrator](it-administrator.md)\.

This section includes tasks that you can complete as a private marketplace administrator through the AWS Marketplace website\. You can also manage private marketplaces using the AWS Marketplace Catalog API\. For more information, see [Working with a private marketplace](https://docs.aws.amazon.com/marketplace-catalog/latest/api-reference/private-marketplace.html) in the *AWS Marketplace Catalog API Reference*\.

## Creating a private marketplace experience<a name="create-your-private-marketplace"></a>

Your private marketplace is made up of one or more private marketplace experiences\. Each experience is associated with one or more accounts in your organization \(if your AWS account is not a member of an organization, then you have one private marketplace experience associated with one account\)\. To create your private marketplace, navigate to [Private Marketplace](https://aws.amazon.com/marketplace/pmp/getstarted), select the **Experiences** page on the left, and choose **Create experience**\.

**Note**  
If your AWS account is part of an organization, then you must create the first private marketplace experience from the management account of your organization\. After it is created, you can manage the experience, or create other experiences from any account that has the correct IAM permissions\.

After you have created your private marketplace, you can return to the private marketplace administration page by selecting **Your Private Marketplace** from the **Hello, <user name>** dropdown in the top right of any AWS Marketplace page\.

Your private marketplace experience is created with no approved products, no branding elements, and is associated with no accounts in your organization\. It is not live by default\. The following topics describe managing your private marketplace experience, including enabling it\.

## Adding products to your private marketplace experience<a name="add-products-to-your-private-marketplace"></a>

**To add products to a private marketplace experience**

1. From the **Private Marketplace** administrator's page, select **Experiences** in the left navigation pane\. Then, on the **Products** tab, choose **All AWS Marketplace products**\. You can search by product name or seller name\.

1. Select the check box next to each product to add to your private marketplace and then choose **Add to Private Marketplace**\.

**Note**  
You can also add a product directly from the product details page by choosing the **Add to Private Marketplace** button on the red banner\. If the red banner is not on the product's detail page, the product is already in your private marketplace\.

You can also add multiple products to multiple experiences at one time by choosing **Bulk add/remove products** from the left navigation pane\.

## Verifying products in your private marketplace experience<a name="verify-product-in-marketplace"></a>

**To verify a product is approved in your private marketplace experience**

1. From the **Private Marketplace** administrator's page, select **Experiences** in the left navigation pane\.

1. Choose **Approved products**\. All approved products display in the approved list\.

**Note**  
If you are using an account that has been associated with the experience you are editing, and the experience is enabled, then you can also view the products directly in the AWS Marketplace console \([https://console\.aws\.amazon\.com/marketplace](https://console.aws.amazon.com/marketplace)\)\. All products in any search results show an *approved for procurement* badge if they are part of your private marketplace\.

## Customizing your private marketplace experience<a name="customize-your-private-marketplace"></a>

On the **Private Marketplace** administrator's page, select **Experiences** in the left navigation pane, and then choose the **Profile** tab to configure your organization’s private marketplace profile\. You can add a logo, add a title, and customize the user interface to use your organization’s color scheme\. Instructions to customize your private marketplace are available on the **Profile** page\. 

## Adding accounts to the private marketplace experience<a name="private-marketplace-account-groups"></a>

A single private marketplace experience can govern one or more accounts in your organization\. To manage this, you can create account groups and associate them with a private marketplace experience\.

An account group is a list of accounts that you want to work with the same experience\. To create an account group, from the **AWS Private Marketplace** administrator's page, select **Account groups** in the left navigation pane\. Choose **Create account group**, and enter the name, description, and list of account IDs for the accounts you want to be in the group\. Select a private marketplace experience to associate the account group with\.

**Note**  
Accounts in organizations are hierarchical\. If you add an account to an account group, its child accounts will be in the account group by default\. You can override this by putting them into another account group that is associated with a different private marketplace experience\.

To create a single account group for all accounts in your organization, you can simply add the root account ID\.

**Note**  
Private marketplace administrators who created a private marketplace prior to January 2021 have a default account group that includes only their organization management account as a member\. This applies to all accounts\. Use the directions above to create additional account groups for other accounts in your organization\.

An account may only be in a single account group\. 

## Configuring your private marketplace<a name="configure-your-private-marketplace"></a>

After you are satisfied with the experience's product list, the marketplace's branding settings, and the associated account groups, then you can make your private marketplace live\. From the **AWS Private Marketplace** administrator's page, select **Experience** in the left navigation pane, then select the experience you want to enable\. On the **Settings** tab, you can change the private marketplace status between **Live** \(enabled\) and **Not live** \(disabled\)\.

You can also choose to allow users to submit software requests with **Software requests**\. If software requests are **On** \(enabled\), end users can choose **Create request** on the product details page to submit a request to the administrator to make the product available on your private marketplace\. Software requests are enabled by default, and the setting can only be modified while the private marketplace is enabled\.

When your private marketplace is live, end users can buy only the products that you have approved\. When your private marketplace is disabled, you retain the list of products\. However, disabling a private marketplace removes the restriction from users in your AWS Organizations organization\. As a result, they can subscribe to any products in the public AWS Marketplace\. 

Making a private marketplace live does not disrupt active Amazon Machine Images \(AMIs\) running on Amazon Elastic Compute Cloud \(Amazon EC2\) instances\. As a best practice, ensure that all AWS Marketplace products currently in use across your organization are included in your private marketplace\. It's also a best practice to have a plan in place to discontinue use of unapproved products before making the private marketplace live\. After the private marketplace is live, all new subscriptions or renewals are governed by the products approved in the private marketplace catalog\.

**Warning**  
Existing product usage may be disrupted when enabling your private marketplace, if those products are not included in the private marketplace\. Users can't subscribe to a product that isn't in your private marketplace, even to replace or update an existing product\.

## Working with private products<a name="private-products-in-a-private-marketplace"></a>

Some products are not publicly available to browse in AWS Marketplace\. These products can only be seen when you are given a private offer from the seller\. The private offer from the seller includes a link to the product\. You can add the product to the private marketplace from the banner at the top of the page\.

**Note**  
If you want to subscribe to a private product from a different account in your organization, the seller must include both your AWS account \(to add the product to the private marketplace\) and the user's account \(to subscribe to the product\) in the private offer\.

To remove a private product from your private marketplace, you must [contact AWS Marketplace Support](https://docs.aws.amazon.com/marketplace/latest/buyerguide/buyer-support.html)\.

## Managing user requests<a name="manage-user-requests-private-marketplace"></a>

You can allow users to submit requests for products to be added to their private marketplace catalog with the software request feature\. To do so, navigate to the administrator's page for your private marketplace, select **Experiences** in the left navigation pane, and choose the experience you want to manage\. From the **Products** tab, choose **Pending requests**\. From here you can review requests your users have made for products to be added to their private marketplace catalog\.

You can add any number of requested products from this page by first selecting the check box next to the name of each requested product, and then choosing **Add to Private Marketplace**\. Similarly, you can also decline one or more selected requests by choosing **Decline**\. To view more information about a product \(or its software request\), choose **View details** in the **Details** column for that request\.

When you decline a product request, you can add a reason and prevent future requests \(block\) for this product\. Blocking a product won't prevent you from adding the product to your private marketplace, but it does prevent your users from requesting the product\.