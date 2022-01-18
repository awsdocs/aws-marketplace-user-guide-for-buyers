# Launching container software from AWS Marketplace<a name="buyer-configuring-a-product"></a>

After you have an active subscription to a container product in AWS Marketplace, the next step is to launch the software by following the instructions included in one of the fulfillment options provided by the seller\. In AWS Marketplace, a *fulfillment option* is an optional seller\-provided procedure for launching their product in your environment\. For container products, the seller can provide up to four fulfillment options, which can use different delivery methods and represent different configurations for the software\. For example, a seller might create one fulfillment option that is a simple configuration used for testing the product, and another fulfillment option to be deployed at scale within an enterprise\. 

 You can see which fulfillment options are available in the **Usage Information** section of the product details page in AWS Marketplace\. Each fulfillment option includes information about which services are supported and provides software version details\. Examples of services include Amazon Elastic Container Service \(Amazon ECS\) and Amazon Elastic Kubernetes Service \(Amazon EKS\)\. You can choose **Usage instructions** to see documentation from the seller about how to use the product, such as how to sign in to a web server, or post\-launch configuration\.

**Note**  
For a walkthrough showing how to subscribe to and deploy a container\-based product, you can also refer to the following videos:  
[ Deploying AWS Marketplace Containers on Amazon ECS Clusters](https://www.youtube.com/watch?v=XaiUAiQQJtk) \(3:34\)
[ Deploying AWS Marketplace Container\-based Products using Amazon ECS Anywhere](https://www.youtube.com/watch?v=9SFjG2UaxXs) \(5:07\)

[![AWS Videos](http://img.youtube.com/vi/https://www.youtube.com/embed/9SFjG2UaxXs/0.jpg)](http://www.youtube.com/watch?v=https://www.youtube.com/embed/9SFjG2UaxXs)

## Launch container software from AWS Marketplace<a name="buyer-launching-a-product"></a>

**To launch container software from AWS Marketplace**

1. Sign in to [AWS Marketplace](https://aws.amazon.com/marketplace)\.

1. Browse AWS Marketplace, and find the product that contains the software you want to launch\. You must have a subscription to the product to launch its software\. For information about finding and subscribing to container products in AWS Marketplace, see [Finding and subscribing to container products](buyer-finding-and-subscribing-to-container-products.md)\.

1. Choose **Continue to Subscribe** on the product details page\.

1. Choose **Continue to Configuration**\. If you don't see the button, you might have to accept terms first, or you might not have a subscription to the product\.

1. In **Fulfillment option**, select a fulfillment option from the seller\-provided list of options\. After selecting a fulfillment option, in **Supported services**, you can see the services that you can launch with the selected option\. For more information about fulfillment options, see [Container product fulfillment options](#buyer-launch-container-fulfillment-options)\.

1. Choose **Continue to Launch**\.

1. Follow the instructions provided by the seller to launch the product\. The instructions are different for each fulfillment option\. For more information, see [Launching with a Container image fulfillment option](#buyer-launch-container-image) or [Launching with a Helm fulfillment option](#buyer-launch-container-helm)\.

1. *Optional \- *Choose **Usage instructions** to see documentation from the seller about how to configure and use the product after launching\.

## Container product fulfillment options<a name="buyer-launch-container-fulfillment-options"></a>

You can see the fulfillment options that are available in the **Usage Information** section of a product's detail page\. Alongside the fulfillment options provided by the seller, AWS Marketplace includes instructions for pulling the docker images directly from Amazon Elastic Container Registry \(Amazon ECR\)\.

Because fulfillment options are provided by the seller, their names and content will be different for each product in AWS Marketplace\. Although the methods are unique to each product and seller, each fulfillment option must have a *delivery method*\. You can think of a delivery method as a fulfillment option type\. The two available delivery methods for container products are **Container image** and **Helm chart**\.

### Launching with a Container image fulfillment option<a name="buyer-launch-container-image"></a>

For a fulfillment option with a **Container image** delivery method, use the seller\-provided instructions to launch the product by pulling docker images directly from Amazon ECR\. The general steps to launch the product are as follows:

1. Ensure that you have installed the latest versions of the AWS Command Line Interface \(AWS CLI\) and Docker\. For more information, see [Using Amazon ECR with the AWS CLI](https://docs.aws.amazon.com/AmazonECR/latest/userguide/getting-started-cli.html) in the *Amazon Elastic Container Registry User Guide*\.

1. Authenticate your Docker client to your Amazon ECR registry\. The steps to do this will depend on your operating system\.

1. Pull all of the docker images using the provided Amazon ECR image Amazon Resource Name \(ARN\)\. For more information, see [Pulling an image](https://docs.aws.amazon.com/AmazonECR/latest/userguide/docker-pull-ecr-image.html) in the *Amazon Elastic Container Registry User Guide*\.

1. Review any usage instructions or external links provided by the seller for information about using the product\.

### Launching with a Helm fulfillment option<a name="buyer-launch-container-helm"></a>

For a fulfillment option with a **Helm** delivery method, use the seller\-provided instructions to launch the product by installing a Helm chart using the Helm CLI\. You can launch the application on an existing Amazon EKS cluster, or a self\-managed cluster on EKS Anywhere, Amazon Elastic Compute Cloud \(Amazon EC2\), or on\-premises\.

**Note**  
The Helm CLI version in your launch environment must be less than 3\.7, for a list of Helm versions, see [Helm releases on GitHub](https://github.com/helm/helm/releases)\.

If the seller has enabled QuickLaunch, you can use it to launch the application\. QuickLaunch is a feature in AWS Marketplace that leverages AWS CloudFormation to quickly create an Amazon EKS cluster and launch the application on it\. For more information about QuickLaunch, see [QuickLaunch in AWS Marketplace](#buyer-launch-container-quicklaunch)\.

The instructions are provided by the seller and are different for each seller and product\. The general steps to launch a product with a Helm fulfillment option are as follows\.

**To launch a product with a Helm fulfillment option**

1. Follow steps 1\-6 of [Launch container software from AWS Marketplace](#buyer-launching-a-product), and choose a fulfillment option with a **Helm chart** delivery method\.

1. In **Deployment target**, choose the environment you want to deploy on:
   + Choose **Amazon managed Kubernetes** to deploy the application in Amazon EKS\. If the seller has enabled QuickLaunch, you can use it to create a new Amazon EKS cluster and launch on it\.
   + Choose **Self\-managed Kubernetes** to deploy the application in [https://anywhere.eks.amazonaws.com/docs/overview/](https://anywhere.eks.amazonaws.com/docs/overview/) or on any Kubernetes cluster running in Amazon EC2 or on\-premises\.

1. If launching in an **Amazon managed Kubernetes** cluster:

   1. To launch on an existing cluster in Amazon EKS, choose **Launch on existing cluster** and follow the provided instructions\. The instructions include creating an AWS Identity and Access Management \(IAM\) role and launching the application\. Ensure that you're using a Helm CLI version less than 3\.7\.

   1. To use QuickLaunch to create a new Amazon EKS cluster and launch on it, choose **Launch on a new Amazon EKS cluster with QuickLaunch**\. Choose **Launch** to be redirected to create a stack in the AWS CloudFormation console\. This stack will create an Amazon EKS cluster and deploy the application by installing the seller\-provided Helm chart\.

   1. On the **Quick create stack** page, in **Stack name**, provide a name for this stack\.

   1. Review the information in the **Parameters** tile and provide any necessary information\. Review and select the acknowledgements in **Capabilities** and choose **Create stack**\.
**Note**  
For more information about QuickLaunch, including information about AWS CloudFormation, stacks, and the created Amazon EKS cluster, see [QuickLaunch in AWS Marketplace](#buyer-launch-container-quicklaunch)\.

1. If launching in a **Self\-managed Kubernetes** cluster:

   1. Ensure that you're using a Helm CLI version less than 3\.7\.

   1. Choose **Create token** to generate a license token and IAM role\. This token and role is used to communicate with AWS License Manager to validate product entitlements\.
**Note**  
The maximum number of license tokens for an account is 10\.

   1. Choose **Download as CSV** to download a \.csv file with the generated token information\. As with all secrets and passwords, store the \.csv file in a secure location\.

   1. Run the commands in **Save as Kubernetes secret** to save the license token and IAM role as a secret in your Kubernetes cluster\. This secret is used when you install the Helm chart and launch the application\. AWS Marketplace uses the secret to verify the entitlement for this product\.

   1. Run the commands in **Launch application using token** to install the Helm chart which deploys the application to your cluster\.

   1. Choose **Usage instructions** to see documentation from the seller about how to configure and use the product after launching\.

   1. *Optional \- *Use the provided commands in **\[Optional\] Download artifacts** to download the product's container images and Helm charts locally\.

## QuickLaunch in AWS Marketplace<a name="buyer-launch-container-quicklaunch"></a>

If the seller has enabled QuickLaunch on a fulfillment option, you can use it to create an Amazon EKS cluster and deploy a container application to it\. With QuickLaunch, you will use AWS CloudFormation to easily configure and create an Amazon EKS cluster and launch a container application on it\. With QuickLaunch, you can quickly launch a container application for testing purposes\. To use QuickLaunch, follow the steps in [Launching with a Helm fulfillment option](#buyer-launch-container-helm)\.

To create an Amazon EKS cluster that the application can be deployed on, you will create a CloudFormation stack\. A *stack* is a collection of AWS resources that you can manage as a single unit\. All the resources in a stack are defined by the stack's CloudFormation template\. In QuickLaunch, the stack's resources include the information o required to create the Amazon EKS cluster and launch the application\. For more information about stacks in AWS CloudFormation, see [Working with stacks](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacks.html) in the *AWS CloudFormation User Guide*\.

After the cluster is created, QuickLaunch launches the application on it by installing the seller\-provided Helm chart onto the cluster\. QuickLaunch handles this for you as part of the stack creation that also creates the Amazon EKS cluster\.