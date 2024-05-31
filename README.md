# aws-rekognition-project
Developed a face recognition system using AWS for precise facial analysis.

Commands:

Install aws-shell
pip install aws-shell

Configure
aws configure

Create a collection on aws rekognition
aws rekognition create-collection --collection-id facerecognition_collection --region us-east-1

Create table on DynamoDB
aws dynamodb create-table --facerec facerecognition \
--attribute-definitions AttributeName=RekognitionId,AttributeType=S \
--key-schema AttributeName=RekognitionId,KeyType=HASH \
--provisioned-throughput ReadCapacityUnits=1,WriteCapacityUnits=1 \
--region us-east-1

Create S3 bucket
aws s3 mb s3://facerecognitionbkt --region us-east-1
