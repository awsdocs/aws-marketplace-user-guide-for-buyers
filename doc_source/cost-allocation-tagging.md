# Cost allocation tagging<a name="cost-allocation-tagging"></a>

AWS Marketplace supports cost allocation tagging for software products that you purchase\. You can use activated cost allocation tags to identify and track AWS Marketplace resource usage through AWS Cost Explorer, AWS Cost and Usage Reports, AWS Budgets, or other cloud cost analysis tools\. To make it easier for you to categorize and track your AWS Marketplace costs, you can use cost allocation tags to organize your resource costs on your cost allocation report\.

Cost allocation tags in AWS Marketplace come from the following two sources:
+ Amazon Machine Image \(AMI\) software product costs that are associated with an Amazon Elastic Compute Cloud \(Amazon EC2\) instance with tags inherit those same tags\. You can activate these tags as cost allocated tags in the AWS Billing and Cost Management console for an account\. For more information about using cost allocation tags with AMI products, see [Cost allocation tagging in AMI products](cost-allocation-tagging-ami-marketplace.md)\.
+ AMI, container, and software as a service \(SaaS\) products may have vendor\-provided tags\. For example, a SaaS product that bills by the number of users could use a tag to identify the usage by department\. For more information about using these tags, see [Vendor\-metered tags](#vendor-metered-tags)\. 

Cost allocation tagging only tracks costs from the time when the tags were activated in the Billing and Cost Management console\. Only AWS account owners, AWS Organizations management account owners, and AWS Identity and Access Management \(IAM\) users with the appropriate permissions can access the Billing and Cost Management console for an account\. Regardless of whether you use cost allocation tagging, there's no change to how much you're billed\. Whether you use cost allocation tags has no impact on the functionality of your AWS Marketplace software products\.

For subscriptions from EMEA\-eligible sellers, the Cost and Usage Report includes a column for the AWS Contracting Party \(Amazon Web Services EMEA SARL\)\.

## Vendor\-metered tags<a name="vendor-metered-tags"></a>

AWS Marketplace products with vendor metering \(including AMI, container, and SaaS products\) might have tags provided by the software vendor as an added service for their customers\. These tags are cost\-allocation tags that help you understand your AWS Marketplace resource usage across vendor\-provided metrics\. You can use these tags to identify and track AWS Marketplace resource usage through AWS Cost Explorer Service, AWS Cost and Usage Report, AWS Budgets, or other cloud cost analysis tools\. 

The tags appear in your AWS Billing console after you start using the AWS Marketplace product and the vendor sends metering records to AWS Marketplace\. If you're using a product based on an upfront commitment in a contract, you won't receive metering usage for the product\. As a result, you won't have the vendor\-metered tags in your AWS Billing console\. If you're managing a linked account, you must have both the `ModifyBilling` and `ViewBilling` permissions to view and activate tags in AWS Billing\. For more information, see [AWS Billing actions policies](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-permissions-ref.html#user-permissions) in the *AWS Billing User Guide*\.

**Note**  
Activating vendor\-metered tags could increase your cost and usage report's size\. Your cost and usage report is stored in Amazon S3\. Therefore, your Amazon S3 costs could increase also\.

**To activate vendor\-metered tags for all eligible AWS Marketplace products**

1. Sign in to the AWS Management Console and open the [AWS Billing console](https://console.aws.amazon.com/billing/)\. Then choose **Cost allocation tags** from the left navigation pane\.

1. Choose the **AWS\-generated cost allocation tags** tab\.

1. Search for `aws:marketplace:isv:` to find tags for all products that support vendor\-metered tagging\.

1. Select the check boxes for all tags, and then choose **Activate**\. Your vendor\-metered tags will go into effect within 24 hours\.

## Related topics<a name="cost-allocation-tagging-related-topics"></a>

For more information, see the following topics:
+ [Using Cost Allocation Tags](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html) in the *AWS Billing User Guide* 
+ [Activating the AWS\-Generated Cost Allocation Tags](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/activate-built-in-tags.html) in the *AWS Billing User Guide* 