# ANALYST SAM APP
### 1. Configure AWS credentials
```bash
$ aws configure
AWS Access Key ID [None]:
AWS Secret Access Key [None]:
Default region name [None]:
Default output format [None]: 
```
### 2. Create basic SAM APP
* **Step 1: Start directory**
```nashorn js
$ sam init
```

* **Step 2: Select options**
    * Select **AWS Quick Start Templates**
    * Choose **Hello World Example** template and download it
    * Use the NodeJs Runtime and zip package type
    * Choose AWS X-Ray, CloudWatch or not
    * Name for application
  
### 3. Sam application structure
* hello_world/app.ts - Contains Lambda function code
* hello_world/requirements.txt - Contains any Node dependencies that your Lambda function requires
* samconfig.toml - Configuration file for application that stores default parameters used by the AWS SAM CLI
* template.yaml - The AWS SAM template that contains application infrastructure code
* .aws-sam - Build folder
  * build/HelloWorldFunction - Contains Lambda function code and dependencies. The AWS SAM CLI creates a directory for each function.
  * build/template.yaml - Contains a copy of AWS SAM template that is referenced by AWS CloudFormation at deployment.
  * build.toml - Configuration file tha stores default parameter values referenced by the AWS SAM CLI when building and deploying application.

### 4. Deploy SAM App
* **Stack Name**: This is AWS CloudFormation stack name. A stack is a collection of AWS resource that you can manage as a single unit.
* **AWS Region**: Region to deploy AWS CloudFormation stack to.
* **Confirm changes** before deploy
* **Allow IAM role creation** - This lets AWS SAM create the IAM role neccessary for API Gateway resource and Lambda function resource to interact.
* **Disable rollback**
* **HelloWorldFunction without authorization defined** - API Gateway endpoint is configured to be publicity accessible, without authorization.
* **Save arguments to configuration file** - This will update application's samconfig.toml file with your deployment preferences
* 

### 5. Command
```bash
  $ sam init
  $ sam build
  $ sam deployed --guided
  # Get all endpoints
  $ sam list endpoints --output json
  # Call API
  $ Callcurl <link>
  # Invoke Lambda function in the cloud
  $ sam remote invoke HelloWorldFunction --stack-name sam-app-begin
  # Sync local changes to the AWS Cloud
  # SAM CLI will confirm and sync to the cloud
  $ sam sync --watch
  # Delete application in the cloud
  $ sam delete
  
```