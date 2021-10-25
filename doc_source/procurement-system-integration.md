# Integrating AWS Marketplace with procurement systems<a name="procurement-system-integration"></a>

You can configure the integration of AWS Marketplace and your Coupa or SAP Ariba procurement software\. After you complete the configuration, users in your organization can use your procurement software to search and request a subscription to AWS Marketplace products\. After the subscription request is approved, the transaction is completed, and the user is notified that the software subscription is available\. When the user signs in to AWS Marketplace, the software product is listed as a purchased subscription and is available for use\. Integration with your procurement system can also integrate your AWS Marketplace invoices with your purchase order system\.

## How procurement integration works<a name="procurement-system-integration-how-it-works"></a>

You can configure procurement software to integrate with AWS Marketplace following the commerce extensible markup language \(cXML\) protocol\. This integration creates an access point into a third party's catalog, known as a *punchout*\. 

The integration differs slightly, based on the procurement system:
+ **Coupa** – Using the Coupa Open Buy feature, you can search AWS Marketplace from within Coupa\. Coupa displays search results, and when the user chooses a product, they're redirected to AWS Marketplace to see the details\. Alternatively, users of Coupa's procurement software can access the AWS Marketplace catalog in the **Shop Online** section of their home page\. The user can also choose to start directly in AWS Marketplace to browse for products\.
+ **SAP Ariba** – Ariba redirects users to AWS Marketplace to search for software and get details about a product\. After an administrator configures the punchout integration, users of Ariba's procurement software can find AWS Marketplace software by choosing the **Catalog** tab, and then selecting the AWS Marketplace catalog\. This redirects them to AWS Marketplace to find the products they're interested in\. 

  Ariba users must initiate their purchase from within Ariba, not AWS Marketplace\.

When the user wants to purchase a subscription that they're browsing in AWS Marketplace, they create a subscription request within AWS Marketplace\. On the product's subscription page, instead of completing the purchase, the user requests approval\. The request is sent back to a shopping cart in the procurement system to complete the approval process\. The following diagram shows the process for a procurement system subscription request\.

 ![\[Flow chart for procurement system subscription request\]](http://docs.aws.amazon.com/marketplace/latest/buyerguide/images/procurement-flow-01.png) 

 When the procurement system receives the request from AWS Marketplace, the procurement system starts a workflow to complete the approval process\. After the request is approved, the procurement system's purchase order system automatically completes the transaction on AWS Marketplace and notifies the user that their subscription is ready to deploy\. The requester doesn't need to return to AWS Marketplace to complete the purchase\. However, they may want to return to AWS Marketplace for instructions on how to use the product they have purchased\. AWS Marketplace sends an email message to the AWS account used to access AWS Marketplace\. The email message informs the recipient that the subscription succeeded and the software is available through AWS Marketplace\. The following diagram shows the approval process for a procurement system subscription request\.

 ![\[Flowchart for procurement system subscription approval\]](http://docs.aws.amazon.com/marketplace/latest/buyerguide/images/procurement-flow-02.png) 

Additional notes about integrating with procurement systems include the following:
+ Free trials don't generate an invoice in the procurement system, because they don't have a charge associated with them\.
+ Contracts that have a one\-time charge in addition to pay\-as\-you\-go charges may require two sets of approvals\. One approval is for the contract \(or annual\) price, and the other for the hourly or per\-unit price \(pay\-as\-you\-go\)\.