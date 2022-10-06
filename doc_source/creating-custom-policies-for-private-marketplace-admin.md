# Creating custom policies for private marketplace administrators<a name="creating-custom-policies-for-private-marketplace-admin"></a>

Your organization can create multiple private marketplace administrators where each administrator is limited to a subset of tasks\. You can tune AWS Identity and Access Management \(IAM\) policies to specify condition keys and resources on AWS Marketplace Catalog API actions listed in [Actions, resources, and condition keys for AWS Marketplace Catalog](https://docs.aws.amazon.com/service-authorization/latest/reference/list_awsmarketplacecatalog.html#awsmarketplacecatalog-catalog_ChangeType)\. The general mechanism to use AWS Marketplace Catalog API change types and resources to tune IAM policies is described in the [AWS Marketplace Catalog API guide](https://docs.aws.amazon.com/marketplace-catalog/latest/api-reference/api-access-control.html)\. For a list of all change types available in the private AWS Marketplace, see [Working with a private marketplace\.](https://docs.aws.amazon.com/marketplace-catalog/latest/api-reference/private-marketplace.html)

To create customer managed policies, see [Creating IAM policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html)\. Following is an example policy JSON that you can use to create an administrator who can only add or remove products from private marketplaces\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:AssociateProductsWithPrivateMarketplace",
                "aws-marketplace:DisassociateProductsFromPrivateMarketplace",
                "aws-marketplace:ListPrivateMarketplaceRequests",
                "aws-marketplace:DescribePrivateMarketplaceRequests"
            ],
            "Resource": [
                "*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:DescribeEntity",
                "aws-marketplace:ListEntities",
                "aws-marketplace:ListChangeSets",
                "aws-marketplace:DescribeChangeSet",
                "aws-marketplace:CancelChangeSet"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:StartChangeSet"
            ],
            "Condition": {
                "StringEquals": {
                    "catalog:ChangeType": [
                        "AllowProductProcurement",
                        "DenyProductProcurement"
                    ]
                }
            },
            "Resource": "*"
        }
    ]
}
```

A policy can also be limited to manage a subset of private marketplace resources\. Following is an example policy JSON you can use to create an administrator who can only manage a specific private marketplace experience\. This example uses a resource string with `exp-1234example` as the `Experience` identifier\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:AssociateProductsWithPrivateMarketplace",
                "aws-marketplace:DisassociateProductsFromPrivateMarketplace",
                "aws-marketplace:ListPrivateMarketplaceRequests",
                "aws-marketplace:DescribePrivateMarketplaceRequests"
            ],
            "Resource": [
                "*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:ListEntities",
                "aws-marketplace:DescribeEntity",
                "aws-marketplace:ListChangeSets",
                "aws-marketplace:DescribeChangeSet",
                "aws-marketplace:CancelChangeSet"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "aws-marketplace:StartChangeSet"
            ],
            "Resource": [
                "arn:aws:aws-marketplace:*:*:AWSMarketplace/Experience/exp-1234example"
            ]
        }
    ]
}
```

For details about how entity identifiers can be retrieved and to view the set of private marketplace resources, see [Working with a private marketplace](https://docs.aws.amazon.com/marketplace-catalog/latest/api-reference/private-marketplace.html)\. 