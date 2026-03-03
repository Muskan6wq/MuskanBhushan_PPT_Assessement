Objective:
Trigger Lambda on S3 events and send notifications using SNS.

Description:
A Lambda function was triggered when a file was uploaded to an S3 bucket. SNS sent an email notification after Lambda execution.
TASK 11 – S3 Upload Email Notification using Lambda and SNS

1. I created an S3 bucket for file upload.

2. I went to SNS service and created a topic.
   - Topic name: topic1
   - Type: Standard

3. I created a subscription for the topic.
   - Protocol: Email
   - Entered my email ID
   - Confirmed the subscription from my email.

4. I went to IAM and created a role for Lambda.
   - Trusted entity: Lambda
   - Attached policies:
     AmazonS3ReadOnlyAccess
     AmazonSNSFullAccess
     AWSLambdaBasicExecutionRole

5. I created a Lambda function.
   - Function name: task11-lambda
   - Runtime: Python
   - Selected the IAM role created earlier.

6. In Lambda code, I wrote Python code to:
   - Get bucket name
   - Get uploaded file name
   - Send message to SNS topic (topic1)

7. I deployed the Lambda function.

8. I added S3 trigger to Lambda.
   - Event type: ObjectCreated (PUT)
   - Selected my S3 bucket
   - Destination: Lambda function

9. In Lambda destination settings:
   - On Success → SNS (topic1)
   - On Failure → None

10. I tested the setup by uploading a file to S3 bucket.

11. After uploading the file, I received an email notification.
    The email contained:
    - Bucket name
    - File name
    - Upload event details

Result:
Whenever a file is uploaded to S3 bucket, Lambda function is triggered,
and an email notification is sent through SNS topic (topic1).
Result:
Event-driven automation implemented successfully.
