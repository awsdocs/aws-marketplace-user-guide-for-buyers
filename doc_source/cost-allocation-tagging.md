# Cost allocation tagging<a name="cost-allocation-tagging"></a>

AWS Marketplace supports cost allocation tagging for software products that you purchase\. You can use activated cost allocation tags to identify and track AWS Marketplace resource usage through AWS Cost Explorer, AWS Cost and Usage Reports, AWS Budgets, or other cloud cost analysis tools\. To make it easier for you to categorize and track your AWS Marketplace costs, you can use cost allocation tags to organize your resource costs on your cost allocation report\.

Cost allocation tags in AWS Marketplace come from the following two sources:
+ Amazon Machine Image \(AMI\) software product costs that are associated with an Amazon Elastic Compute Cloud \(Amazon EC2\) instance with tags inherit those same tags\. You can activate these tags as cost allocated tags in the AWS Billing and Cost Management console for an account\. For more information about using cost allocation tags with AMI products, see [Cost allocation tagging in AMI products](cost-allocation-tagging-ami-marketplace.md)\.
+ AMI, container, and software as a service \(SaaS\) products may have vendor\-provided tags\. For example, a SaaS product that bills by the number of users could use a tag to identify the usage by department\. For more information about using these tags, see [Vendor\-metered tags](#vendor-metered-tags)\. 

Cost allocation tagging only tracks costs from the time when the tags were activated in the Billing and Cost Management console\. Only AWS account owners, AWS Organizations management account owners, and AWS Identity and Access Management \(IAM\) users with the appropriate permissions can access the Billing and Cost Management console for an account\. Regardless of whether you use cost allocation tagging, there's no change to how much you're billed\. Whether you use cost allocation tags has no impact on the functionality of your AWS Marketplace software products\.

For subscriptions from EMEA\-eligible sellers, the Cost and Usage Report includes a column for the AWS Contracting Party \(Amazon Web Services EMEA SARL\)\.

## Vendor\-metered tags<a name="vendor-metered-tags"></a>

AWS Marketplace products with vendor metering \(including AMI, container, and SaaS products\) may have tags provided by the software vendor\. These tags are cost\-allocation tags that help you understand your AWS Marketplace resource usage across vendor\-provided metrics\.

Some things to remember when you use vendor\-metered tags include the following:
+ Find vendor\-metered tags in the Billing and Cost Management console \(available at [ https://console\.aws\.amazon\.com/billing/home](https://console.aws.amazon.com/billing/home)\) by choosing **Cost allocation tags**, and then the **AWS\-generated cost allocation tags** tab\.
+ Vendor\-metered tag key names start with `aws:marketplace:isv:` to make them easier to find\.
+ Before you can use vendor\-metered tags to track your usage as cost allocation tags, you must activate them in the Billing and Cost Management console\.

## Related topics<a name="cost-allocation-tagging-related-topics"></a>

For more information, see the following topics:
+ [Using Cost Allocation Tags](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html) in the *AWS Billing User Guide* 
+ [Activating the AWS\-Generated Cost Allocation Tags](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/activate-built-in-tags.html) in the *AWS Billing User Guide* 