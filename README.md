# quarkus-aws-lambda-hello-world project

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

Install [SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)

## Packaging and running the application

Build the project and create a container image using the following command

`mvn package -Pnative -Dquarkus.native.container-build=true -Dquarkus.container-image.build=true`

Locally invoke the Lambda function using

`sam local invoke --template target/sam.native.yaml --event payload.json`.
