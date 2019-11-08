# Creating and Managing a Private Marketplace<a name="private-catalog-administration"></a>

 To create and manage a private marketplace you must have the IAM permissions found in the `AWSPrivateMarketplaceAdminFullAccess` IAM policy\. For information on applying this policy to IAM users, groups, and roles, see [Creating a Private Marketplace IT Administrator](it-administrator.md)\.

## Creating Your Private Marketplace<a name="create-your-private-marketplace"></a>

 To create your private marketplace, navigate to [Private Marketplace](https://aws.amazon.com/marketplace/pmp/getstarted) and choose **Create a Private Marketplace**\.

## Adding Products to Your Private Marketplace<a name="add-products-to-your-private-marketplace"></a>

 To add products to your organization’s private marketplace: 

1.  From the **Private Marketplace** administrator's page, on the **Products** tab, choose **All AWS Marketplace products**\. You can search by product name or vendor name to find a product to add to your private marketplace\.

1.  Select the check box next to each product that you want to add to your private marketplace and then choose **Add to Private Marketplace**\.

 To verify that a product is in your private marketplace, from the **Private Marketplace** search page, search for the product that you added and choose it\. You are redirected to the product detail page for that product\. If the product isn't in your private marketplace, a red banner appears at the top of the page\. To add the product to your private marketplace, choose **Add** in the red banner\. 

 You can return to the **Private Marketplace** administrator's page at any time to add or remove other products\. 

## Managing User Requests<a name="manage-user-requests-private-marketplace"></a>

You can allow users to submit requests for products to be added to your private marketplace with the software request feature\. To do so, navigate to the administrator's page for your private marketplace, and from the **Products** tab, choose **Pending requests**\. From here you can review a table of existing requests your users have made for products they'd like added to your private marketplace\.

You can add any number of requested products from this page by first selecting the checkbox next to the name of each requested product, and then choosing **Add to Private Marketplace**\. Similarly, you can also decline one or more selected requests by choosing **Decline**\. To view more information about a product \(or its software request\) choose **View details** in the **Details** column for that request in the table\.

When you decline a product request, you've got the option of adding a reason and to prevent future requests for this product on your private marketplace\. This won't prevent you from adding the product to your private marketplace, but it will prevent your users from requesting the product\.

## Customizing Your Private Marketplace<a name="customize-your-private-marketplace"></a>

On the **Private Marketplace** administrator's page, you can choose the **Profile** tab to configure your organization’s private marketplace profile\. You can add a logo, create a custom welcome message, and customize to use your organization’s color scheme\. Instructions to customize your private marketplace are available on the profile page\. 

## Configuring Your Private Marketplace<a name="configure-your-private-marketplace"></a>

 After you are satisfied with your product list and your look and feel, enable your private marketplace\. To enable or disable your private marketplace, from the **AWS Private Marketplace** administrator's page, under **Private Marketplace status**, you can toggle the private marketplace status between **live** and **Not live**\.

You can also allow users to submit software requests with the **Software requests** toggle\. When your private marketplace is live, members of your organization can subscribe only to the products that you added to your private marketplace\. When your private marketplace is disabled, you retain the list of products\. However, disabling removes the procurement restriction control from users in your AWS Organizations organization\. 