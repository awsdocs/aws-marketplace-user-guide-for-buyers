# API Reference<a name="api-reference"></a>

 You can use this reference to build private images using the AWS Marketplace Image Build Service API\. The AWS account that you use to build a private image must have the IAM permissions specified in the `AWSMarketplaceImageBuildFullAccess` or `AWSMarketplaceFullAccess` managed policies\. You can use an existing role or create a new role using this\. To add the `AWSMarketplaceImageBuildFullAccess` policy to a user, group or role: 

1.  Sign in to the AWS Management Console and open the AWS IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\. 

1.  In the navigation pane of the AWS IAM console, choose **Policies**\. 

1.  Next to **Filter policies**, enter *AWSMarketplaceImageBuildFullAccess*\. The policy should be listed in the results\. 

1.  In the **Results** pane, choose **AWSMarketplaceImageBuildFullAccess**\. 

1.  In the **Policy actions** pulldown menu, choose **Attach**\. 

1.  Select the users, groups and roles you want to attach this policy to, and then choose **Attach Policy**\. 

**Note**  
Three of the actions described in the `AWSMarketplaceImageBuildFullAccess` policy are performed on your behalf by AWS Marketplace for using private image builds\. Those actions are defined below:  
**aws\-marketplace:ListBuilds** – Retrieves information about build records for all builds associated with the AWS account in use\. Note that you can only retrieve information about builds you own\.
**aws\-marketplace:StartBuilds** – Initiates a build that installs the specified AWS Marketplace product on the source AMI, creating a new AMI in the same AWS Region\.
**aws\-marketplace:DescribeBuilds** – Retrieves information about all build records associated with the input build identifiers\. Maximum number of build identifiers in an call is 50\.

With the permissions defined by these policies in place, the next time that a user or member of a group or role you selected accesses the AWS Marketplace website, they can perform private image build related tasks\.

## Building a Private Image Using the CLI<a name="building-a-private-image-using-the-cli"></a>

 Configure your CLI by creating a JSON file using the following code, and then executing the following command\. 

 **Code** 

```
<![CDATA[{
  "version":"2.0",
  "metadata":{
    "apiVersion":"2017-12-15",
    "endpointPrefix":"imagebuild.marketplace",
    "jsonVersion":"1.1",
    "protocol":"json",
    "serviceAbbreviation":"Marketplace Image Build",
    "serviceFullName":"AWS Marketplace Image Build Service",
    "serviceId":"Marketplace Image Build",
    "signatureVersion":"v4",
    "signingName":"aws-marketplace",
    "targetPrefix":"AWSMPImageBuilding",
    "uid":"marketplaceimagebuild-2017-12-15"
  },
  "operations":{
    "DescribeBuilds":{
      "name":"DescribeBuilds",
      "http":{
        "method":"POST",
        "requestUri":"/"
      },
      "input":{"shape":"DescribeBuildsRequest"},
      "output":{"shape":"DescribeBuildsResult"},
      "errors":[
        {"shape":"InternalServerErrorException"},
        {"shape":"InvalidNextTokenException"},
        {"shape":"InvalidMaxResultsException"},
        {"shape":"InvalidFilterException"}
      ],
      "documentation":"<p>Retrieves information about build records for all builds associated with the AWS account in use, including status, explanation, and the id of the resulting AMI. The results are in descending order of creation time. You can filter results by build id, status and fulfillment option id. Use the pagination parameters to retrieve results in a set of sequential pages. You can only retrieve information about builds you own.</p>"
    },
    "StartBuild":{
      "name":"StartBuild",
      "http":{
        "method":"POST",
        "requestUri":"/"
      },
      "input":{"shape":"StartBuildRequest"},
      "output":{"shape":"StartBuildResult"},
      "errors":[
        {"shape":"InternalServerErrorException"},
        {"shape":"BuildLimitExceededException"},
        {"shape":"IdempotentParameterMismatchException"},
        {"shape":"InstallerMismatchException"},
        {"shape":"InvalidFulfillmentOptionIdException"},
        {"shape":"InvalidSourceImageIdException"},
        {"shape":"InvalidDestinationImageNameException"},
        {"shape":"InvalidSnsTopicArnException"},
        {"shape":"UnauthorizedOperationException"}
      ],
      "documentation":"<p>Initiates a build that installs the specified Marketplace product on the source AMI, creating a new AMI in the same region.</p>"
    }
  },
  "shapes":{
    "Build":{
      "type":"structure",
      "members":{
        "BuildId":{
          "shape":"String",
          "documentation":"<p>Unique identifier for a build.</p>"
        },
        "DestinationImage":{
          "shape":"DestinationImage",
          "documentation":"<p>Details about the new image to be created in the same region.</p>"
        },
        "FulfillmentOptionIds":{
          "shape":"StringList",
          "documentation":"<p>List of fulfillment option ids of Marketplace software products to install on the image.They need to be retrieved from the Marketplace Website.</p>"
        },
        "Products":{
          "shape":"ProductList",
          "documentation":"<p>Details about the Marketplace software products to install on the image. This structure is populated by Marketplace.</p>"
        },
        "SourceImage":{
          "shape":"SourceImage",
          "documentation":"<p>Details about the existing source image on which to install the software product.</p>"
        },
        "SnsTopicArn":{
          "shape":"String",
          "documentation":"<p>The full ARN of the SNS topic that will be notified when the build status changes.</p>"
        },
        "Status":{
          "shape":"BuildStatus",
          "documentation":"<p>Current status of the build. Possible build statuses include the following:</p> <ul> <li> <p>InProgress - A new build has been defined and started.</p> </li> <li> <p>InternalError - The build was terminated due to a retryable error.</p> </li> <li> <p>Failed - The build has failed and a new image has not been created.</p> </li> <li> <p>Succeeded - The build has finished and a new image has been created.</p> </li> </ul>"
        },
        "StandardOutputUrl":{
          "shape":"String",
          "documentation":"<p> A presigned S3 URL to the logs emitted by the installer on STDOUT during install process.</p>"
        },
        "StandardErrorUrl":{
          "shape":"String",
          "documentation":"<p> A presigned S3 URL to the logs emitted by the installer on STDERR during install process.</p>"
        },
        "ErrorDetail":{"shape":"ErrorDetail"},
        "StartTime":{
          "shape":"DateTime",
          "documentation":"<p>Time stamp indicating when the build was created, in ISO 8601 format.</p>"
        },
        "LastUpdateTime":{
          "shape":"DateTime",
          "documentation":"<p>Time stamp indicating when the build was last updated, in ISO 8601 format.</p>"
        }
      },
      "documentation":"<p>Container for the properties describing each build that meets the filter requirements.</p>"
    },
    "BuildLimitExceededException":{
      "type":"structure",
      "members":{
        "Message":{"shape":"String"}
      },
      "documentation":"<p>This exception is thrown when the number of concurrent builds exceeds the maximum allowed.</p>",
      "exception":true
    },
    "BuildList":{
      "type":"list",
      "member":{"shape":"Build"}
    },
    "BuildStatus":{
      "type":"string",
      "enum":[
        "InProgress",
        "InternalError",
        "Failed",
        "Succeeded"
      ]
    },
    "DateTime":{"type":"timestamp"},
    "DescribeBuildsRequest":{
      "type":"structure",
      "members":{
        "BuildIds":{
          "shape":"StringList",
          "documentation":"<p>List of unique build identifiers.</p>"
        },
        "NextToken":{
          "shape":"NextToken",
          "documentation":"<p>(Optional) Token that indicates the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.</p>"
        },
        "MaxResults":{
          "shape":"MaxResults",
          "documentation":"<p>(Optional) An upper limit on the number of build descriptions that can be returned.</p>"
        },
        "Filters":{
          "shape":"FilterList",
          "documentation":"<p>(Optional) One or more filters. Possible values are: </p> <ul> <li> <p>build-id - A unique identifier which refers to a particular build.</p> </li> <li> <p>fulfillment-option-id - A fulfillment option identifier which refers to a set of builds.</p> </li> <li> <p>product-id - A product identifier which refers to a set of builds.</p> </li> <li> <p>status - Build status (in-progress | internal-error | failed | succeeded) which refers to a set of builds.</p> </li> </ul>"
        }
      },
      "documentation":"<p>Container for request parameters to the DescribeBuilds operation.</p>"
    },
    "DescribeBuildsResult":{
      "type":"structure",
      "members":{
        "NextToken":{
          "shape":"NextToken",
          "documentation":"<p>Token that indicates the start of the next sequential page of results.</p>"
        },
        "Builds":{
          "shape":"BuildList",
          "documentation":"<p>List of builds, which hold properties describing each build that meets the filter requirements.</p>"
        }
      },
      "documentation":"<p>Container for the result of the DescribeBuilds operation.</p>"
    },
    "DestinationImage":{
      "type":"structure",
      "members":{
        "Id":{
          "shape":"String",
          "documentation":"<p>The id of the new image on which the software product has been installed.</p>"
        },
        "Description":{
          "shape":"String",
          "documentation":"<p>A description for the new image to be created in the same region.</p>"
        },
        "Name":{
          "shape":"String",
          "documentation":"<p>A name for the new image.</p> <p>Constraints: 3-128 alphanumeric characters, parentheses (()), square brackets ([]), spaces ( ), periods (.), slashes (/), dashes (-), single quotes ('), at-signs (@), or underscores(_)</p>"
        }
      },
      "documentation":"<p>Details about the new image to be created in the same region.</p>"
    },
    "ErrorCode":{
      "type":"string",
      "documentation":"<ul> <li> <p>SSMAgentNotFound - Error code representing condition when either SSM agent was not running on the instance or was unreachable.</p> </li> <li> <p>InstallFailed - Error code representing condition when installation timed out or exited with non zero return value.</p> </li> </ul>",
      "enum":[
        "SSMAgentNotFound",
        "InstallFailed"
      ]
    },
    "ErrorDetail":{
      "type":"structure",
      "members":{
        "Code":{
          "shape":"ErrorCode",
          "documentation":"<p>Error code providing specific detail on the error.</p>"
        },
        "Message":{
          "shape":"String",
          "documentation":"<p>Error message providing specific detail on the error.</p>"
        }
      },
      "documentation":"<p>A container for error code and an error message.</p>"
    },
    "Filter":{
      "type":"structure",
      "members":{
        "Name":{
          "shape":"String",
          "documentation":"<p>The name of the filter. Filter names are case-sensitive.</p>"
        },
        "Values":{
          "shape":"StringList",
          "documentation":"<p>One or more filter values. Filter values are case-sensitive.</p>"
        }
      },
      "documentation":"<p>A filter name and value pair that is used to return a more specific list of results. Filters can be used to match a set of resources by various criteria, such as tags, attributes, or ids.</p>"
    },
    "FilterList":{
      "type":"list",
      "member":{"shape":"Filter"}
    },
    "IdempotentParameterMismatchException":{
      "type":"structure",
      "members":{
        "Message":{"shape":"String"}
      },
      "documentation":"<p>This exception is thrown when an idempotent operation is retried and the parameters do not match the original call with the same idempotency token.</p>",
      "exception":true
    },
    "InstallerMismatchException":{
      "type":"structure",
      "members":{
        "Message":{"shape":"String"}
      },
      "documentation":"<p>This exception is thrown when the specified fulfillment option id is not compatible with the platform of the specified source image id.</p>",
      "exception":true
    },
    "InternalServerErrorException":{
      "type":"structure",
      "members":{
        "Message":{"shape":"String"}
      },
      "documentation":"<p>This exception is thrown on an internal server error.</p>",
      "exception":true,
      "fault":true
    },
    "InvalidDestinationImageNameException":{
      "type":"structure",
      "members":{
        "Message":{"shape":"String"}
      },
      "documentation":"<p>This exception is thrown when the specified destination image name does not meet the constraints.</p>",
      "exception":true
    },
    "InvalidFilterException":{
      "type":"structure",
      "members":{
        "Message":{"shape":"String"}
      },
      "documentation":"<p>This exception is thrown when the specified filter does not exist.</p>",
      "exception":true
    },
    "InvalidFulfillmentOptionIdException":{
      "type":"structure",
      "members":{
        "Message":{"shape":"String"}
      },
      "documentation":"<p>This exception is thrown when the specified fulfillment option id does not exist.</p>",
      "exception":true
    },
    "InvalidMaxResultsException":{
      "type":"structure",
      "members":{
        "Message":{"shape":"String"}
      },
      "documentation":"<p>This exception is thrown when the specified value for maximum number of results to be returned is not valid.</p>",
      "exception":true
    },
    "InvalidNextTokenException":{
      "type":"structure",
      "members":{
        "Message":{"shape":"String"}
      },
      "documentation":"<p>This exception is thrown when the specified next token is not valid.</p>",
      "exception":true
    },
    "InvalidSnsTopicArnException":{
      "type":"structure",
      "members":{
        "Message":{"shape":"String"}
      },
      "documentation":"<p>This exception is thrown when the specified SNS topic ARN does not exist.</p>",
      "exception":true
    },
    "InvalidSourceImageIdException":{
      "type":"structure",
      "members":{
        "Message":{"shape":"String"}
      },
      "documentation":"<p>This exception is thrown when the specified source image id does not exist.</p>",
      "exception":true
    },
    "MaxResults":{
      "type":"integer",
      "max":256,
      "min":0
    },
    "NextToken":{
      "type":"string",
      "max":1024,
      "min":1
    },
    "Product":{
      "type":"structure",
      "members":{
        "Id":{
          "shape":"String",
          "documentation":"<p>The id of the Marketplace software product to install on the image. This field is populated by Marketplace.</p>"
        },
        "Version":{
          "shape":"String",
          "documentation":"<p>The version of the Marketplace software product to install on the image. This field is populated by Marketplace.</p>"
        },
        "Title":{
          "shape":"String",
          "documentation":"<p>The title of the Marketplace software product to install on the image. This field is populated by Marketplace.</p>"
        }
      },
      "documentation":"<p>Details about the Marketplace software product to install on the image. This structure is populated by Marketplace.</p>"
    },
    "ProductList":{
      "type":"list",
      "member":{"shape":"Product"}
    },
    "SourceImage":{
      "type":"structure",
      "members":{
        "Id":{
          "shape":"String",
          "documentation":"<p>The id of the existing source image.</p>"
        },
        "Name":{
          "shape":"String",
          "documentation":"<p>The name of the existing source image.</p>"
        }
      },
      "documentation":"<p>Details about the existing source image on which to install the software product</p>"
    },
    "StartBuildRequest":{
      "type":"structure",
      "required":[
        "FulfillmentOptionIds",
        "SourceImageId",
        "DestinationImageName"
      ],
      "members":{
        "ClientToken":{
          "shape":"String",
          "documentation":"<p>(Optional) Unique, case-sensitive identifier you provide to ensure idempotency of the request. We recommend UUID.</p>",
          "idempotencyToken":true
        },
        "FulfillmentOptionIds":{
          "shape":"StringList",
          "documentation":"<p>List of fulfillment option ids of Marketplace software products to install on the image.They need to be retrieved from the Marketplace Website.</p>"
        },
        "SourceImageId":{
          "shape":"String",
          "documentation":"<p>The id of the image on which to install the software product.</p>"
        },
        "DestinationImageName":{
          "shape":"String",
          "documentation":"<p>A name for the new image.</p> <p>Constraints: 3-128 alphanumeric characters, parentheses (()), square brackets ([]), spaces ( ), periods (.), slashes (/), dashes (-), single quotes ('), at-signs (@), or underscores(_)</p>"
        },
        "DestinationImageDescription":{
          "shape":"String",
          "documentation":"<p>(Optional) A description for the new image in the same region.</p>"
        },
        "SnsTopicArn":{
          "shape":"String",
          "documentation":"<p>(Optional) The full ARN of the SNS Topic that will be notified when the build status changes.</p>"
        }
      },
      "documentation":"<p>Container for request parameters to the StartBuild operation.</p>"
    },
    "StartBuildResult":{
      "type":"structure",
      "members":{
        "BuildId":{
          "shape":"String",
          "documentation":"<p>Unique identifier for the started build.</p>"
        },
        "Products":{
          "shape":"ProductList",
          "documentation":"<p>Details about the Marketplace software products to install on the image. This structure is populated by Marketplace.</p>"
        }
      },
      "documentation":"<p>Container for the result of the StartBuild operation.</p>"
    },
    "String":{"type":"string"},
    "StringList":{
      "type":"list",
      "member":{"shape":"String"}
    },
    "UnauthorizedOperationException":{
      "type":"structure",
      "members":{
        "Message":{"shape":"String"}
      },
      "documentation":"<p>This exception is thrown when the IAM principal referred to by the request credentials does not have appropriate permissions.</p>",
      "exception":true
    }
  },
  "documentation":"<fullname>AWS Marketplace Image Build Service</fullname> <p>AWS Marketplace customers can use this API to build new images and to retrieve information about all of their builds.</p>"
}]]>
```

 **Command** 

```
$ aws configure add-model --service-model file:<insert path to
      marketplaceimagebuild-2017-12-15.normal.json> --service-name
      marketplaceimagebuild
```

 To start a build, execute the following code\. Note that you must first create the Amazon S3 bucket that you want to use, called *awsexamplebucket* in this example\.

```
$ aws marketplaceimagebuild start-build \
      --input-fulfillment-option-ids "fo-ids4xf7qagwyc" \ 
      --input-image-id ami-58d7e821 \ 
      --output-image-name "ubuntu-ami" \ 
      --output-image-description "Ubuntu" \ 
      --input-instance-type "m4.xlarge" \ 
      --output-installation-log-s3-bucket-name "awsexamplebucket" \ 
      --input-automation-role SSMAutomationRole \ 
      --input-instance-profile SSMInstanceRole 
      --region eu-west-1
{
    "BuildId": "d33cffa8-b49a-42b7-b98b-54c41ca26b3a",
    "Status": "InProgress"
}
```

 To describe a build, execute the following code\. 

```
$ aws marketplaceimagebuild describe-builds --build-ids "1f84f17b-35c6-4e5b-9170-c98f279c6345" --region=us-west-2
{"Builds": 
  [
    {"BuildId": "1f84f17b-35c6-4e5b-9170-c98f279c6345", 
     "InputFulfillmentOptions": 
      [
        {"Id": "fo-ids4xf7qagwyc", 
         "Product": 
          {"Title": "Test Ubuntu product", 
           "Version": "Test 1.0"}
        }
      ], 
     "InputImage": 
      {"Id": "ami-86743afe", 
       "Name": "Ubuntu 16.04"}, 
     "LastUpdateTime": 1529960569.43, 
     "OutputImage": 
      {"Description": "Ubuntu 16.04", 
       "Name": "Ubuntu"}, 
     "OutputInstallationLogS3BucketName": "awsexamplebucket", 
     "StartTime": 1529960569.43, 
     "Status": "InProgress"}, 
  ]
}
```

 To access documentation, execute the following command\. 

```
$ aws marketplaceimagebuild help
```

## Using the AWS SDK for Java<a name="using-the-aws-sdk-for-java"></a>

 To install the AWS SDK for Java: 

1.  Download the [AWS SDK for Java](https://aws.amazon.com/sdk-for-java/)\. 

1.  Create a new project using your IDE and add the AWS SDK for Java JAR as a library\. 

1.  Verify that everything is linked correctly by calling an existing AWS service\. 

1.  Download the JAR and add it as a library to your project\. 

1.  Verify that you can call AWSMarketplaceImageBuild\. 