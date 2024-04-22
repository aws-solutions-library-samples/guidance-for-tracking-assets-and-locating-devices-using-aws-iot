# Guidance for Tracking Assets & Locating Devices Using AWS IoT

The Guidance title should be consistent with the title established first in Alchemy.

**Example:** *Guidance for Product Substitutions on AWS*

This title correlates exactly to the Guidance it’s linked to, including its corresponding sample code repository. 


## Table of Contents


1. [Overview](#overview-required)
    - [Cost](#cost)
2. [Prerequisites](#prerequisites-required)
    - [Operating System](#operating-system-required)
3. [Deployment Steps](#deployment-steps-required)
4. [Deployment Validation](#deployment-validation-required)
5. [Running the Guidance](#running-the-guidance-required)
6. [Next Steps](#next-steps-required)
7. [Cleanup](#cleanup-required)
8. [FAQ, known issues, additional considerations, and limitations](#faq-known-issues-additional-considerations-and-limitations-optional)
9. [Revisions](#revisions-optional)
10. [Notices](#notices-optional)


## Overview (required)

This Guidance demonstrates how to stream location data from your assets and devices with Internet of Things (IoT) sensors, helping you record and monitor the movement of your assets through a centralized management system. IoT-enabled devices, such as a smart bicycle, a delivery truck, or a shipping container, can be configured with AWS IoT Core, a fully managed service that lets you connect billions of IoT devices and route trillions of message topics to AWS. These message topics can then interface with a host of other AWS services, such as Amazon Location Service, which helps you add location data to your message topics. Other AWS services can be configured with this Guidance to alert you for geofencing events, allow you to receive location updates, and help you visualize asset positions from an interactive web application.

The demo contained in this repository configures the resources needed to send and visualize location updates via AWS IoT Core. An optional template also defines a basic analytics setup where location updates are stored in Amazon S3 for future analysis.

### Cost

You are responsible for the cost of the AWS services used while running this Guidance. As of April 2024, the cost for running this Guidance with the default settings in the US East (N. Virginia) region is approximately $94.80 per month for processing 1 million location updates.

The majority of the cost is location writes and retrievals from Amazon Location Service. Depending on how updates are [filtered](https://aws.amazon.com/blogs/mobile/amazon-location-service-enables-position-filtering-to-reduce-position-jitter-and-cost-of-tracking/) the cost to retrieve location updats may be less.

## Prerequisites
### Operating System

In order to visualize device positions and geofences, the application requires a local web server to be running. This deployment will assume the usage of Amazon Linux 2023 using AWS Cloud9. Running these steps on other operating systems may require additional steps. Additionally, the AWS Command Line Interface (CLI) will be required to deploy CloudFormation templates, and Node.js for running the visualization.

### AWS Account Requirements

This deployment requires access to the following resources:

**Example resources:**
- Amazon Location Service
- Amazon EventBridge
- Amazon Data Firehose
- AWS Lambda
- Amazon S3
- Amazon SNS
- AWS IoT Core
- Amazon Cognito
- IAM roles with specific permissions
- Access to a Region that suppors this deployment [Default: US East (N. Virginia)]

### Service limits

Amazon Location Service supports a default limit of 50 Device Position Updates per second. If you anticipate updating at a higher rate, this limit can be increased via the [quota increase process](https://docs.aws.amazon.com/servicequotas/latest/userguide/request-quota-increase.html)

### Supported Regions

This guidance supports the following regions:

- US East (Ohio) - us-east-2
- US East (N Virgina) - us-east-1
- US West (Oregon) - us-west-2
- Asia Pacific (Mumbai) - ap-south-1
- Asia Pacific (Singapore) - ap-southeast-1
- Asia Pacific (Sydney) - ap-southeast-2
- Asia Pacific (Tokyo) - ap-northeast-1
- Canada (Central) - ca-central-1
- Europe (Frankfurt) - eu-central-1
- Europe (Ireland) - eu-west-1
- Europe (London) - eu-west-2
- Europe (Stockholm) - eu-north-1
- South America (Sao Paulo) - sa-east-1
- AWS GovCloud (US-West) - us-gov-west-1


## Deployment Steps
**1. Clone guidance and visualization repositories**

1. In a terminal, enter `git clone https://github.com/aws-solutions-library-samples/guidance-for-asset-tracking-using-aws-iot-core-and-amazon-location-services.git --recurse-submodules`
2. Navigate to `guidance-for-asset-tracking-using-aws-iot-core-and-amazon-location-services`


**2. Install Visualization prerequisites**

1. Navigate to the `amazon-location-samples-react/tracking-data-streaming` and run `npm install` to install required packages.
2. 

## Deployment Validation

<Provide steps to validate a successful deployment, such as terminal output, verifying that the resource is created, status of the CloudFormation template, etc.>


**Examples:**

* Open CloudFormation console and verify the status of the template with the name starting with xxxxxx.
* If deployment is successful, you should see an active database instance with the name starting with <xxxxx> in        the RDS console.
*  Run the following CLI command to validate the deployment: ```aws cloudformation describe xxxxxxxxxxxxx```



## Running the Guidance

<Provide instructions to run the Guidance with the sample data or input provided, and interpret the output received.> 

This section should include:

* Guidance inputs
* Commands to run
* Expected output (provide screenshot if possible)
* Output description



## Next Steps (required)

Provide suggestions and recommendations about how customers can modify the parameters and the components of the Guidance to further enhance it according to their requirements.


## Cleanup (required)

- Include detailed instructions, commands, and console actions to delete the deployed Guidance.
- If the Guidance requires manual deletion of resources, such as the content of an S3 bucket, please specify.



## FAQ, known issues, additional considerations, and limitations (optional)


**Known issues (optional)**


## Revisions (optional)

- First Release

## Notices

*Customers are responsible for making their own independent assessment of the information in this Guidance. This Guidance: (a) is for informational purposes only, (b) represents AWS current product offerings and practices, which are subject to change without notice, and (c) does not create any commitments or assurances from AWS and its affiliates, suppliers or licensors. AWS products or services are provided “as is” without warranties, representations, or conditions of any kind, whether express or implied. AWS responsibilities and liabilities to its customers are controlled by AWS agreements, and this Guidance is not part of, nor does it modify, any agreement between AWS and its customers.*

