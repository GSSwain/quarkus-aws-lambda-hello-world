# quarkus-aws-lambda-hello-world project

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

Install [SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)

## Packaging and running the application

Build the project and create a container image using the following command

`mvn package -Pnative -Dquarkus.native.container-build=true -Dquarkus.container-image.build=true`

Locally invoke the Lambda function using

`sam local invoke --template target/sam.native.yaml --event payload.json`.

## Deployment

One needs an AWS Access key id, Secret access key, Region and a Lambda role to be set in the following environment varibales respectively AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, AWS_DEFAULT_REGION and LAMBDA_ROLE_ARN


You can also use `aws configure` for setting AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY and AWS_DEFAULT_REGION  as well.

Create a Lambda execution role and attach an apporpriate role policy by following the below URL

https://docs.aws.amazon.com/lambda/latest/dg/lambda-intro-execution-role.html

Finally run the below command to create the lambda function on AWS

`bash target/manage.sh native create`