# aws-opensearch-bedrock-layer

This project contains source code and supporting files for creating a Lambda Layer.
The use-case here is a layer that dependecies to interface with Amazon Opensearch and AWS Bedrock services. In addition to these, langchain library is also added.

- layers - Makefile and requirements.txt to build Lambda layers
- template.yaml - A template that defines Lambda Layer

## Build Lambda layer

The Serverless Application Model Command Line Interface (SAM CLI) is an extension of the AWS CLI that adds functionality for building and testing Lambda applications. It uses Docker to run your functions in an Amazon Linux environment that matches Lambda. It can also emulate your application's build environment and API.

To use the SAM CLI, you need the following tools.

* SAM CLI - [Install the SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)
* [Python 3 installed](https://www.python.org/downloads/)
* Docker - [Install Docker community edition](https://hub.docker.com/search/?type=edition&offering=community)

To build  your application for the first time, run the following in your shell:

```bash
sam build --use-container
```

The SAM CLI installs dependencies defined in `layers/opensearch-bedrock/requirements.txt`, creates a deployment package, and saves it in the `.aws-sam/build` folder.


## Resources

See the [AWS SAM developer guide](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/what-is-sam.html) for an introduction to SAM specification, the SAM CLI, and serverless application concepts.

Next, you can use AWS Serverless Application Repository to deploy ready to use Apps that go beyond hello world samples and learn how authors developed their applications: [AWS Serverless Application Repository main page](https://aws.amazon.com/serverless/serverlessrepo/)

## Package the layer
```
zip -r ./bin/opensearch_bedrock_layer.zip ./.aws-sam/build/OpensearchBedrockLayer
```
or on windows
```
7z a -tzip ./bin/opensearch_bedrock_layer.zip ./.aws-sam/build/OpensearchBedrockLayer
```