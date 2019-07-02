# APIGatewayExamples
Examples for interacting with AWS API Gateway


Bucket=rboyd-query-multistring
sam build -u -t ./Lambda_Swagger/swagger_lambda_integration.yaml -b ./build/ \
&& sam package --s3-bucket $Bucket --template-file build/template.yaml --output-template-file build/packaged.yaml --profile acct2\
&& aws cloudformation deploy --template-file build/packaged.yaml --stack-name swagger-lambda --capabilities CAPABILITY_IAM --profile acct2