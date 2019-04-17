# Security on AWS Marketplace<a name="buyer-security"></a>

 We list software from high\-quality vendors, and actively work to maintain the quality of our selection\. Because every customer is different, our goal is to provide enough information about the products listed on AWS Marketplace so that customers can make good purchasing decisions\. 

## What Information Do You Share with the Software Seller about the Customers of a Product?<a name="what-information-do-you-share-with-the-software-seller-about-the-customers-of-a-product"></a>

 We may share your contact information with our sellers if it is necessary for them \(i\) to provide customer training and technical support and \(ii\) for software activation, configuration and customization of Content \(iii\) compensate their sales teams internally\. In addition, we may share information such as company name, full address and usage fees with sellers in order for sellers to compensate their sales teams\. We may also share certain information with vendors to help them evaluate the effectiveness of their marketing campaigns\. Sellers may use this information along with information that they already possess to determine rewards for their sales teams or usage on a customer\-by\-customer basis\. Otherwise, we generally do not share customer information with sellers, and any information shared is not personally identifiable, unless \(i\) you have given us permission to share such information, or \(ii\) we believe that providing the information to sellers is necessary to comply with laws or regulations\.

## How Do I Control Access to My AWS Marketplace Subscriptions?<a name="how-do-i-control-access-to-my-aws-marketplace-subscriptions"></a>

 Use AWS Identity and Access Management \(IAM\) to create IAM users and assign them permissions to work with your subscriptions\. This can include listing subscriptions, subscribing to software, and launching instances of subscribed software\. Others can then log in to AWS Marketplace using the user name and password that you give them, and they have only the permissions that you assigned\.

## As an IAM User, How Do I Log In and Work with Subscriptions?<a name="as-an-iam-user-how-do-i-log-in-and-work-with-subscriptions"></a>

 If your organization is using IAM, your account owner probably set you up with user information that includes account credentials and a URL for logging in\. The URL looks like `https://123456789012.signin.aws.amazon.com/console` but with a different number\. After you have the URL and credentials, navigate to the login URL, log in using your credentials, and navigate to [AWS Marketplace](https://aws.amazon.com/marketplace)\. The owner might have restricted the tasks that you can perform\.

## Why Do I Get a Permission Denied Error When I Try to Subscribe to Software or Start an Instance?<a name="why-do-i-get-a-permission-denied-error-when-i-try-to-subscribe-to-software-or-start-an-instance"></a>

 When the IAM account administrator set up your user information, they granted you certain permissions\. If you try to perform a task in AWS Marketplace that the owner hasn't allowed, you get this error\. Contact your account administrator for more information\. 