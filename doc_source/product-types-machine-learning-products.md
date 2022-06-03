# Machine learning products<a name="product-types-machine-learning-products"></a>

 AWS Marketplace has a category for machine learning products you can subscribe to through AWS Marketplace\. The product category is Machine Learning\. The products in this category include machine learning \(ML\) model packages and algorithms\. 

 You can browse and search for hundreds of ML model packages and algorithms from a broad range of subcategories, such as computer vision, natural language processing, speech recognition, text, data, voice, image, video analysis, fraud detection, and predictive analysis\. 

 To assess the quality and suitability of a model, you can review product descriptions, usage instructions, customer reviews, sample [Jupyter notebooks](https://docs.aws.amazon.com/sagemaker/latest/dg/nbi.html), pricing, and support information\. You deploy models directly from the Amazon SageMaker console, through a Jupyter notebook, with the Amazon SageMaker SDK, or using the AWS Command Line Interface AWS CLI\. Amazon SageMaker provides a secure environment to run your training and inference jobs by running a static scan on all marketplace products\. 

## Amazon SageMaker model package<a name="model-package-overview"></a>

 An **Amazon SageMaker *model package*** is a unique pretrained ML model that is identified by an Amazon Resource Name \(ARN\) on Amazon SageMaker\. Customers use a model package to create a model in Amazon SageMaker\. Then, the model can be used with hosting services to run real\-time inference or with batch transform to run batch inference in Amazon SageMaker\.

The following diagram shows the workflow for using model package products\. 

1. On AWS Marketplace, you find and subscribe to a model package product\. 

1. You deploy the inference component of the product in SageMaker to perform inference \(or prediction\) in real time or in batches\. 

![\[Diagram of how a buyer uses a model package from AWS Marketplace.\]](http://docs.aws.amazon.com/marketplace/latest/buyerguide/images/buyer-ml-model.png)

## Amazon SageMaker algorithm<a name="algorithm-overview"></a>

An **Amazon SageMaker *algorithm*** is a unique Amazon SageMaker entity that is identified by an ARN\. An algorithm has two logical components: training and inference\. 

The following diagram shows the workflow for using algorithm products\. 

1. On AWS Marketplace, you find and subscribe to an algorithm product\. 

1. You use the training component of the product to create a training job or tuning job using your input dataset in Amazon SageMaker to build machine learning models\. 

1. When the training component of the product completes, it generates the model artifacts of the machine learning model\. 

1. SageMaker saves the model artifacts in your Amazon Simple Storage Service \(Amazon S3\) bucket\. 

1. In SageMaker, you can then deploy the inference component of the product using those generated model artifacts to perform inference \(or prediction\) in real time or in batches\. 

![\[Diagram of how a buyer uses a SageMaker algorithm from AWS Marketplace.\]](http://docs.aws.amazon.com/marketplace/latest/buyerguide/images/buyer-ml-algorithm.png)

## Find, subscribe, and deploy<a name="machine-learning-find-subscribe-and-deploy"></a>

The following diagram shows an overview of the process to find, subscribe, and deploy a machine learning product on Amazon SageMaker\.

1. Find and try a model from AWS Marketplace

1. Subscribe to the ML product

1. Deploy models in Amazon SageMaker

1. Use secure REST APIs

1. Perform
   + Real\-time inference
   + Batch transform job

![\[Diagram of how a buyer finds, buys and deploys a machine learning product.\]](http://docs.aws.amazon.com/marketplace/latest/buyerguide/images/buyer-ml-deploy-model.png)

You pay only for your usage, with no minimum fees or upfront commitments\. AWS Marketplace provides a consolidated bill for algorithms and model packages, and AWS infrastructure usage charges\. 

The following sections explain how to find, subscribe to, and deploy an ML product\.

**Topics**
+ [Finding a machine learning product](#finding-ml-products)
+ [Subscribing to a machine learning product](#subscribing-to-ml-products)
+ [Deploying a machine learning product](#deploying-ml-products)

### Finding a machine learning product<a name="finding-ml-products"></a>

**To find Amazon SageMaker model packages and algorithms**

1. Sign in to the [AWS Marketplace website](https://aws.amazon.com/marketplace/search/results?page=1&filters=fulfillment_options&fulfillment_options=SAGEMAKER)\.

1. Under **Find AWS Marketplace products that meet your needs**, use the **Categories** dropdown menu to find the subcategory under **Machine Learning** that you are interested in\. 

1. You can refine your search results by applying resource type, category, and pricing filters\. 

1. From the search results, access the product detail page\. 

1. Review the product description, usage instructions, customer reviews, data requirements, sample Jupyter notebooks, and pricing and support information\. 

### Subscribing to a machine learning product<a name="subscribing-to-ml-products"></a>

**To subscribe to Amazon SageMaker model packages and algorithms**

1. From the product detail page, choose **Continue to subscribe**\. 

1. On the procurement page, review the product pricing information and the end user license agreement \(EULA\)\. 

1. Choose **Continue to subscribe**\.

### Deploying a machine learning product<a name="deploying-ml-products"></a>

**To deploy Amazon SageMaker model packages and algorithms**

1. Confirm that you have a valid subscription to the algorithm or model package by navigating to [Your Marketplace Software](https://aws.amazon.com/marketplace/ai/library?productType=ml&ref_=lbr_tab_ml)\. 

1. Configure the product \(for example, by selecting a specific version or deployment region\) on the AWS Marketplace website\. 

   After you subscribe to either a model package product or algorithm product, it’s added to your product list in the SageMaker console\. You can also use AWS SDKs, the AWS Command Line Interface \(AWS CLI\), or the SageMaker console to create a fully managed REST inference endpoint or perform inference on batches of data\. 

1. View the Amazon SageMaker product detail page by choosing **View in Amazon SageMaker**\. 

1. From the Amazon SageMaker console, you can deploy the model packages and algorithms using the Amazon SageMaker console, Jupyter notebook, Amazon SageMaker CLI commands, or API operations\.

For more information about deploying on Amazon SageMaker, see [Getting Started](https://docs.aws.amazon.com/sagemaker/latest/dg/gs.html)\. 