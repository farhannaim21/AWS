# AWS
# AWS Lambda Functions Project

This project includes two AWS Lambda functions designed to execute specific tasks on the AWS cloud platform. The functions are written in Python and deployed using AWS Lambda.

---

## Function Descriptions

### 1. **Function 1: [Function Name]**
- **Purpose**: Briefly describe the primary task of this Lambda function (e.g., "Processes incoming API requests and saves data to DynamoDB").
- **Triggers**: Mention the event source (e.g., API Gateway, S3 event, DynamoDB stream).
- **Output**: Describe the output or result of the function (e.g., "Stores processed data in DynamoDB and returns a confirmation message").

### 2. **Function 2: [Function Name]**
- **Purpose**: Briefly describe the primary task of this Lambda function (e.g., "Sends email notifications based on processed data").
- **Triggers**: Mention the event source (e.g., SNS topic, CloudWatch event).
- **Output**: Describe the output or result of the function (e.g., "Sends email via SES and logs results to CloudWatch").

---

## Deployment

### Prerequisites
1. Install the [AWS CLI](https://aws.amazon.com/cli/).
2. Install [AWS SAM CLI](https://aws.amazon.com/serverless/sam/).
3. Set up an IAM role with the necessary permissions for your Lambda functions.

### Steps to Deploy
1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/<your-repo>.git
   cd <your-repo>
2.Package the Lambda functions:
aws cloudformation package \
    --template-file template.yaml \
    --s3-bucket <your-s3-bucket> \
    --output-template-file packaged-template.yaml
3. Deploy the Lambda functions:
  aws cloudformation deploy \
    --template-file packaged-template.yaml \
    --stack-name <your-stack-name> \
    --capabilities CAPABILITY_IAM

    
Directory Structure
aws-lambda-project/
│
├── lambda_functions/
│   ├── function_1/
│   │   ├── app.py                # Main handler for function 1
│   │   └── requirements.txt      # Dependencies for function 1
│   ├── function_2/
│   │   ├── app.py                # Main handler for function 2
│   │   └── requirements.txt      # Dependencies for function 2
│
├── template.yaml                 # CloudFormation template for both functions
└── README.md                     # Project documentation


Testing Locally
Install the required dependencies for each function:
pip install -r lambda_functions/function_1/requirements.txt -t lambda_functions/function_1/
pip install -r lambda_functions/function_2/requirements.txt -t lambda_functions/function_2/


Use AWS SAM CLI to invoke the functions:
sam local invoke Function1Name --event events/event1.json
sam local invoke Function2Name --event events/event2.json

Logging and Monitoring
Logs for each Lambda function are available in Amazon CloudWatch. Access the logs by navigating to the CloudWatch Logs section in the AWS Management Console and selecting the respective log group for each function.

Troubleshooting
Ensure that the IAM role associated with the Lambda functions has the necessary permissions.
Verify that the S3 bucket exists and the name matches in the template.yaml.
Use the CloudWatch logs to debug errors.
License
This project is licensed under the MIT License. See the LICENSE file for details.

Developed by Farhan Naim.

vbnet
Copy code

### Instructions to Use:
1. Replace placeholders like `<your-username>`, `<your-repo>`, `<your-s3-bucket>`, `<your-stack-name>` with your specific details.
2. Add this `README.md` file to the root of your project directory and commit it to your GitHub repository.

Let me know if you'd like any further adjustments!
