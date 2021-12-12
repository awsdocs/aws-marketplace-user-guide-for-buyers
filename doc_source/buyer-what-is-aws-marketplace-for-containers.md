# Container products<a name="buyer-what-is-aws-marketplace-for-containers"></a>

Container products are standalone products fulfilled as container images\. Container products can either be free or must be paid for using a seller\-provided pricing option\. Container products can be used with multiple container runtimes and services, including [Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/) \(Amazon ECS\), [Amazon Elastic Kubernetes Service](https://docs.aws.amazon.com/eks/latest/userguide/) \(Amazon EKS\), and even services running on your own infrastructure\. For a complete list of supported runtimes and services with more information about each, see [Supported services for container products](buyer-finding-and-subscribing-to-container-products.md#buyer-container-product-launch-environments)\.

You can discover, subscribe to, and deploy container products on the AWS Marketplace website or in the Amazon ECS console\. You can deploy many products to Amazon ECS or Amazon EKS by using seller\-supplied deployment templates, such as task definitions or Helm charts\. Or, you can access container images directly from private [Amazon Elastic Container Registry](https://docs.aws.amazon.com/AmazonECR/latest/userguide/) \(Amazon ECR\) repositories after you have subscribed to those products\.

If a product has enabled QuickLaunch, you can use it to quickly test container products on an Amazon EKS cluster with just a few steps\. QuickLaunch uses AWS CloudFormation to create an Amazon EKS cluster and launch container software on it\. For more information about launching with QuickLaunch, see [QuickLaunch in AWS Marketplace](buyer-configuring-a-product.md#buyer-launch-container-quicklaunch)\.

This section provides information about finding, subscribing to, and launching container products in AWS Marketplace\.

## Pricing models for paid container products<a name="what-is-aws-marketplace-for-containers-pricing"></a>

Paid container products must have one or more pricing models\. Like with any other paid products in AWS Marketplace, you're billed for paid container products by AWS according to the pricing model\. The pricing model might be a fixed monthly fee or an hourly price, monitored in seconds and prorated\. Pricing details will be shown on the detail page and when you subscribe to the product\.

The supported pricing models for container products in AWS Marketplace are as follows:
+ A fixed monthly charge that provides unlimited usage\.
+ An upfront charge for usage of the product for the duration of a long term contract\.
+ A pay\-as\-you\-go model \(typically hourly\) based on usage of the product\.
+ A pay\-up\-front model with contract pricing\.

For more information about each model, see [Container product pricing](https://docs.aws.amazon.com/marketplace/latest/userguide/pricing-container-products.html) in the *AWS Marketplace Seller Guide*\.

## Overview of containers and Kubernetes<a name="buyer-introduction-to-docker-containers-and-kubernetes"></a>

 Containers, such as [Docker](https://docs.aws.amazon.com/AmazonECR/latest/userguide/docker-basics.html) containers, are an open\-source software technology that provides an additional layer of abstraction and automation over virtualized operating systems such as Linux and Windows Server\. Just as virtual machines are instances of server images, containers are instances of Docker container images\. They wrap server application software in a file system that contains everything it needs to run: code, runtime, system tools, system libraries, and so on\. With containers, the software always runs the same, regardless of its environment\. 

Analogous to Java virtual machines, containers require an underlying platform to provide a translation and orchestration layer while being isolated from the operating system and each other\. There are different Docker\-compatible runtimes and orchestration services that you can use with Docker containers, including Amazon ECS, which is a highly scalable, high\-performance orchestration service for AWS, and Amazon EKS, which makes it easy to deploy, manage, and scale containerized applications using [Kubernetes](https://docs.aws.amazon.com/eks/latest/userguide/), an open source management and orchestration service\.