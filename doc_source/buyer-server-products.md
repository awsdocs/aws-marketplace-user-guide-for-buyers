# AMI\-based server products<a name="buyer-server-products"></a>

An Amazon Machine Image \(AMI\) is an image of a server, including an operating system and often additional software, which runs on AWS\.

The software listed in AWS Marketplace is only available to run on Amazon Elastic Compute Cloud \(Amazon EC2\)\. It's not available for download\. 

 On AWS Marketplace, you can search for AMIs \(with search suggestions\), view product reviews submitted by other customers, subscribe and launch AMIs, and manage your subscriptions\. All AWS Marketplace products have been verified for quality and pre\-configured for 1\-Click launch capability on Amazon Web Services \(AWS\) infrastructure\. 

 Both AMI and software as a service \(SaaS\) product listings are from trusted sellers\. AMI products run within a customer's AWS account\. You retain more control over software configuration and over the servers that run the software, but you also have additional responsibilities regarding server configuration and maintenance\. 

The AWS Marketplace catalog contains a curated selection of open source and commercial software from well\-known sellers\. Many products on AWS Marketplace can be purchased by the hour\. 

 The AMI catalog is a community resource where people and development teams can list and exchange software or projects under development, without having to go through extensive vetting\. Listings in the community AMI catalog may or may not be from well\-known sellers and generally have not undergone additional investigations\. 

 An AWS Marketplace product contains one AMI for each AWS Region in which the product is available\. These AMIs are identical except for their location\. Additionally, when sellers update their product with the latest patches and updates, they may add another set of AMIs to the product\. 

 Some AWS Marketplace products may launch multiple instances of an AMI because they're deployed as a cluster using AWS CloudFormation templates\. This cluster of instances, along with additional AWS infrastructure services configured by the CloudFormation template, act as a single product deployment\. 

## AWS CloudFormation template<a name="what-is-aws-cloudformation"></a>

 AWS CloudFormation is a service that helps you model and set up your AWS resources so that you can spend less time managing those resources and more time focusing on your applications that run in AWS\. A CloudFormation template describes the various AWS resources that you want, such as Amazon Elastic Compute Cloud \(Amazon EC2\) instances or Amazon Relational Database Service \(Amazon RDS\) database instances\. CloudFormation takes care of provisioning and configuring those resources for you\. For more information, see [Getting started with AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/GettingStarted.html)\. 

### Using AWS CloudFormation templates<a name="using-CF-templates"></a>

Software sellers may offer CloudFormation templates to define a preferred deployment topology consisting of multiple AMI instances and other AWS resources\. If a CloudFormation template is available for a product, it will be listed as a deployment option on the product listing page\. 

You can use an AMI to deploy a single Amazon EC2 instance\. You can use a CloudFormation template to deploy multiple instances of an AMI that act as a cluster—along with AWS resources such as Amazon RDS, Amazon Simple Storage Service \(Amazon S3\), or any other AWS service—as a single solution\. 

**Topics**
+ [AWS CloudFormation template](#what-is-aws-cloudformation)
+ [AMI subscriptions](buyer-ami-subscriptions.md)
+ [AMI products with contract pricing](buyer-ami-contracts.md)
+ [Metering\-enabled AMI products](buyer-ami-metering-enabled-products.md)
+ [Cost allocation tagging in AMI products](cost-allocation-tagging-ami-marketplace.md)
+ [Private image build](buyer-private-image-build.md)
+ [Using AMI aliases](buyer-ami-aliases.md)