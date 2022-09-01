# Viewing a product's security profile with AWS Marketplace Vendor Insights<a name="buyer-vendor-view-profile"></a>

 AWS Marketplace Vendor Insights gathers security data from vendors and helps buyers ensure that they procure trusted software that continuously meets industry standards\. By integrating with AWS Audit Manager, AWS Marketplace Vendor Insights can automatically pull up\-to\-date security information for your software\-as\-a\-service \(SaaS\) products on AWS Marketplace\. AWS Marketplace Vendor Insights integrates with AWS Artifact so that you can access on\-demand compliance reports for your vendor software, alongside reports for AWS services\. It also integrates with AWS Security Hub to send findings, such as changes to the security status of vendor software, to AWS Security Hub, so you can take appropriate risk mitigation actions\.

## Dashboard in AWS Marketplace Vendor Insights<a name="dashboard-vendor-insights"></a>

The dashboard presents the compliance artifacts and security control information for a software product assessed by AWS Marketplace Vendor Insights\. AWS Marketplace Vendor Insights gathers the evidence\-based information for the 10 security controls categories that are presented on the dashboard\. For more information about the controls categories, see [Control categories ](#vendor-insights-data-control-categories)\.

## View the security profile of a SaaS product in AWS Marketplace Vendor Insights<a name="view-data"></a>

AWS Marketplace Vendor Insights helps you make decisions about vendor software\. AWS Marketplace Vendor Insights extracts data from a vendor's evidence\-based information from 10 control categories and multiple controls\. You can view profile and summary information for a product on the dashboard or select control categories to learn more about data gathered about the product\.

**To view the security profile of a SaaS product in AWS Marketplace Vendor Insights**

1. Sign in to the AWS Management Console and open the [AWS Marketplace console](https://console.aws.amazon.com/marketplace/)\.

1. Choose **Vendor Insights**\.

1. From **Vendor Insights**, choose a product\. 

1. On the **Product detail ** page, choose the **Security and compliance** tab\.
**Note**  
A number in a red circle indicates the number of noncompliant controls\.

1. For **Control categories**, choose the text under any of the listed categories to view more information\. 

   For example, for **Audit, Compliance and Security Policy**, choose **3 controls**\. View the list of certifications or download reports\.

   For example, for **Data security and privacy**, choose **4 controls**\. View the list of controls and status\.
   + Choose the first control name \(**Do you have a policy/procedure to ensure compliance with applicable legislative, regulatory and contractual requirements?**\)\.
   + Read the information presented\. You can also view reports from AWS Artifact or view exceptions from the auditor\.
   + Select the product name in the navigation above to return to the **Product detail** page\.

## Control categories<a name="vendor-insights-data-control-categories"></a>

AWS Marketplace Vendor Insights uses 10 control categories with multiple control sets and controls within each control\. The following table provides details of the structure of the data\. Each control is listed according to the category with description and value details\.


**Summary of control categories for security**  

| Control category | Number of control sets  | Number of controls | 
| --- | --- | --- | 
| Access management  | 4 | 20 | 
| Application security | 4 | 22 | 
| Audit and compliance | 3 | 5 | 
| Business resiliency | 3 | 15 | 
| Data security and privacy  | 6 | 20 | 
| End user device and mobile security | 4 | 15 | 
| Human resources  | 1 | 7 | 
| Infrastructure security  | 3 | 13 | 
| Risk management and incident response | 4 | 18 | 
| Security and configuration policy | 2 | 5 | 
| Total | 34 | 140 | 