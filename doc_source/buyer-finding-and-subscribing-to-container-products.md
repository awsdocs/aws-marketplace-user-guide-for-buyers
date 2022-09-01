# Finding and subscribing to container products<a name="buyer-finding-and-subscribing-to-container-products"></a>

 Container products are products in AWS Marketplace that can be launched on container images\. Container products include any product in AWS Marketplace in which the seller has provided a fulfillment option with a **Container image** or **Helm chart** delivery method\. For more information about container product delivery methods, see [Container product delivery methods](#buyer-container-product-delivery-methods)\. 

Many launch environments, also known as supported services, are available for fulfillment options in container products\. Launch environments include services such as Amazon Elastic Container Service \(Amazon ECS\), Amazon Elastic Kubernetes Service \(Amazon EKS\) and even your own self\-managed infrastructure\. For a complete list of available container product launch environments, see [Supported services for container products](#buyer-container-product-launch-environments)\.

## Browse container products using the AWS Marketplace website<a name="buyer-browsing-product-details"></a>

 You can browse container products by using the [AWS Marketplace website](https://aws.amazon.com/marketplace/)\.

**To browse container products using the AWS Marketplace website**

1. Navigate to the [AWS Marketplace search page](https://aws.amazon.com/marketplace/search/?)\.

1. Filter **Delivery method** by **Container image** or **Helm chart**\.

1. \(Optional\) Filter **Supported services** to narrow the search results by the services that the product can be launched with\.

 After you find a product that you're interested in, choose the title to navigate to the product details page\.

### Container product details page<a name="buyer-browsing-product-details-page"></a>

In the product details page in AWS Marketplace, you can find details about the product, including the following information:
+ **Product Overview** – The overview includes a product description and the following information:
  + The product version you're viewing\.
  + A link to the seller's profile\.
  + The product categories this product belongs to\.
  + The supported operating systems to run this software\.
  + The delivery methods that are available for launching the software\.
  + The supported services that this product can be launched on\.
+ **Pricing Information** – Products can be free, Bring Your Own License \(BYOL\), pay\-up\-front with contract pricing, or pay\-as\-you\-go with either a fixed monthly or annual price, or an hourly price\. For more information about pricing models, see [Container product pricing](https://docs.aws.amazon.com/marketplace/latest/userguide/pricing-container-products.html) in the *AWS Marketplace Seller Guide*\.
+ **Usage Information** – Included here are seller\-provided fulfillment options with instructions to launch and run the software\. Each product must have at least one fulfillment option and can have up to five\. Each fulfillment option includes a delivery method and instructions to be followed to launch and run the software\.
+ **Support Information** – This section includes details about how to get support for the product and its refund policy\.
+ **Customer Reviews** – Find reviews for the product from other customers or write your own\.

To subscribe to a product, choose **Continue to Subscribe** on the product's details page\. For more information about subscribing to products, see [Subscribing to products](#buyer-subscribing-to-container-products)\.

## Subscribing to products<a name="buyer-subscribing-to-container-products"></a>

 If you want to use a product, you must subscribe to it first\. On the subscription page you can view pricing information for paid products and access the end\-user license agreement \(EULA\) for the software\.

For a product with container contract pricing, select your contract pricing and choose **Accept Contract** to proceed\. This creates a *subscription* to the product, which provides an *entitlement* to use the software\. It will take a minute or two for the subscription to complete\. After you receive an entitlement to a paid product, you will be charged when you start using the software\. If you cancel your subscription without terminating all running instances of the software, you will continue to be charged for any software usage\. You may also incur infrastructure charges related to using the product\. For example, if you create a new Amazon EKS cluster to host the software product, you will be charged for that service\. 

**Note**  
For a walkthrough showing how to subscribe to and deploy a container\-based product, you can also refer to the following videos:  
[ Deploying AWS Marketplace Containers on Amazon ECS Clusters](https://www.youtube.com/watch?v=XaiUAiQQJtk) \(3:34\)
[ Deploying AWS Marketplace Container\-based Products using Amazon ECS Anywhere](https://www.youtube.com/watch?v=9SFjG2UaxXs) \(5:07\)

## Container product delivery methods<a name="buyer-container-product-delivery-methods"></a>

A product in AWS Marketplace is considered a container product if the seller has provided at least one fulfillment option with either a **Container image** or **Helm chart** delivery method\.

### Container image delivery method<a name="buyer-container-product-delivery-methods-image"></a>

For a fulfillment option with a **Container image** delivery method, use the seller\-provided instructions to launch the product by pulling docker images directly from the AWS Marketplace registry on Amazon Elastic Container Registry\. For more information about launching with this delivery method, see [Launching with a Container image fulfillment option](buyer-configuring-a-product.md#buyer-launch-container-image)\.

### Helm chart delivery method<a name="buyer-container-product-delivery-methods-helm"></a>

For a fulfillment option with a **Helm chart** delivery method, use the seller\-provided instructions or deployment template to launch the product by installing a Helm chart using the Helm CLI\. You can launch the application on an existing Amazon EKS cluster, or a self\-managed cluster on EKS Anywhere, Amazon Elastic Compute Cloud \(Amazon EC2\), or on\-premises\. For more information about launching with this delivery method, see [Launching with a Helm fulfillment option](buyer-configuring-a-product.md#buyer-launch-container-helm)\.

## Supported services for container products<a name="buyer-container-product-launch-environments"></a>

The following list includes all of the supported services for container products in AWS Marketplace\. A *supported service* is a container service or environment where the product can be launched\. A container product must include at least one fulfillment option that includes a delivery method with instructions to launch to one or more of the environments\.

### Amazon ECS<a name="buyer-container-product-launch-environments-ecs"></a>

Amazon Elastic Container Service \(Amazon ECS\) is a highly scalable, fast container management service that you can use to run, stop, and manage containers on a cluster\. Your containers are defined in a task definition that you use to run individual tasks or tasks within a service\. In this context, a service is a configuration that enables you to run and maintain a specified number of tasks simultaneously in a cluster\. You can run your tasks and services on a serverless infrastructure that is managed by AWS Fargate\. Alternatively, for more control over your infrastructure, you can run your tasks and services on a cluster of Amazon EC2 instances that you manage\.

For more information about Amazon ECS, see [What is Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html) in the *Amazon Elastic Container Service Developer Guide*\.

### Amazon EKS<a name="buyer-container-product-launch-environments-eks"></a>

Amazon Elastic Kubernetes Service \(Amazon EKS\) is a managed service that you can use to run Kubernetes on AWS without needing to install, operate, and maintain your own Kubernetes control plane or nodes\. Kubernetes is an open\-source system for automating the deployment, scaling, and management of containerized applications\.

For more information about Amazon EKS, see [What is Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html) in the **Amazon EKS User Guide**\.

### Self\-managed Kubernetes<a name="buyer-container-product-launch-environments-self"></a>

You can launch container products on self\-managed Kubernetes clusters running in EKS Anywhere, Amazon ECS Anywhere, Amazon EC2, or on\-premises infrastructure\.

Amazon ECS Anywhere is a feature of Amazon ECS that you can use to run and manage container workloads on customer\-managed infrastructure\. Amazon ECS Anywhere builds upon Amazon ECS to provide a consistent tooling and API experience across your container\-based applications\.

For more information, see [Amazon ECS Anywhere](https://aws.amazon.com/ecs/anywhere/)\.

 EKS Anywhere is a service that you can use to create an Amazon EKS cluster on customer\-managed infrastructure\. You can deploy EKS Anywhere as a simple, unsupported local environment or as a production\-quality environment that can become a supported on\-premises Kubernetes platform\.

For more information about EKS Anywhere, see the [EKS Anywhere documentation](https://anywhere.eks.amazonaws.com/docs/overview/)\.

## Browse container products using the Amazon ECS console<a name="buyer-amazon-ecs-console"></a>

 You can also find container products in the Amazon ECS console\. The navigation pane has links to discover new products from AWS Marketplace and to see existing subscriptions\.

## Canceling a subscription<a name="buyer-cancelling-a-subscription"></a>

 To cancel a subscription to a product, use the **Your Software** page\. 