# Development

## Git Repository
>https://github.com/jacobbishop1000/video-crime-miner

## Tech aspects

Tech stack is:
- Angular
- Ionic
- Node
- Amazon Rekognition
- Amazon S3 Bucket
- Amazon SQS
- Amazon SNS
- Amazon Cognito
- PostgreSQL

## Technologies Needed

- NodeJS (npm) >= 19.0.0
- PostgreSQL >= 15.0

 
## Required IDEs, Frameworks

- No required IDE
- Need a terminal to use git, npm, psql
- Angular is the JS framework used for the frontend

## Cloning project and initial configurations

1. In your terminal, move to desired folder location for the project. 
2. run **'git clone https://github.com/jacobbishop1000/video-crime-miner'**
3. move into the folder **'{project root}/video-crime-miner/node-video-crime-miner/'** and run **'npm run build'** to start backend client
3. move into the folder **'{project root}/video-crime-miner/angular-video-crime-miner/'** and run **'npm run build-site'** to start frontend client

## Folder Structure

- **angular-video-crime-miner/**: contains configuration files for angular/typescript
    - **angular-video-crime-miner/node_modules/** contains node dependencies after npm install
    - **angular-video-crime-miner/src/**: source code for front-end site
        - **angular-video-crime-miner/src/app/**:  html, scss, and angular scripts for each of the site modules
        - - **angular-video-crime-miner/src/assets/**:  a small .csv file containing all currently accepted Rekognition labels
- **node-video-crime-miner**: source code for aws node clients, also contains configuration files for node/typescript
    - **node-video-crime-miner/resources/**: contains a few sample files for testing uploads to s3 buckets and video analysis
    - **node-video-crime-miner/src/**:
        - **node-video-crime-miner/src/AWS Layer/**: contains source code for creating and managing new clients for s3, sqs, sns, rekognition
        - **node-video-crime-miner/src/cli/**: simple command line interface to interact with files in s3 buckets and handle jobs from rekognition
    - **node-video-crime-miner/test/**: contains the test files for s3, rekognition, sqs/sns client interaction
    - **node-video-crime-miner/node_modules/** contains node dependencies after npm install
    - **node-video-crime-miner/out/** folder contains compiled code from TypeScript to JavaScript

## Important config files

Node/Angular Configuration

- **angular-video-crime-miner/angular.json**
    - contains build information (build parameters, dependencies) for Angular
- **angular-video-crime-miner/package.json**
    - contains build information (build parameters, dependencies) for Angular
- **node-video-crime-miner/package.json**
    - contains build information (build parameters, dependencies) for Node

Typescript Configuration
- **angular-video-crime-miner/tsconfig.json**
    - contains TypeScript settings for Angular
- **node-video-crime-miner/tsconfig.json**
    - contains TypeScript settings for Node

>*Both of these tsconfig files have additional tsconfig.spec.json and tsconfig.app.json. The contents of these files will be treated as if they were appended to the contents of tsconfig.json*

Environment Variable Configuration
- **node-video-crime-miner/.env**
    - contains important environment variables that cannot be stored in source code

Jest Configuration
- **node-video-crime-miner/jest.config.js**
    - contains settings for jest test suite

## How to Test and Interpret the Results
**For Express-Node**
1. Open a new terminal and move to the folder **{project root}/video-crime-miner/node-video-crime-miner/**

2. make sure to have run **'npm run build'** in this folder

3. run **'npm run test'** to run Jest tests
    > if Jest gives errors, make sure your version of node is >= 19.0.0
    >
    > IMPORTANT: Make sure that you have a proper .env file with all required variables (seen below) as some will be needed for integration testing
    > #Testing Postgres 
    TEST_POSTGRES_USER=postgres
TEST_POSTGRES_HOST=localhost
TEST_POSTGRES_PASSWORD=password
TEST_POSTGRES_DB=test-video-crime-miner
TEST_POSTGRES_PORT=5432

4. The terminal output displays test results with visual aids (green check marks, red x's, etc.)

**For Angular**
1. Open a new terminal and move to the folder **{project root}/video-crime-miner/angular-video-crime-miner/**

2. Run **'npm run test-site'** to run Karma tests

3. Interpret results by seeing if Karma shows any errors inside the Chrome window that pops up

## Building a database

1. Open a new terminal and move to the folder **{project root}/video-crime-miner/node-video-crime-miner/**

2. run **'npm run remake-database'**, and there will be a locally stored and ran postgresql database

3. add the following values to your .env file
` #Database
DBHOST=localhost
DBUSER=postgres
DB=video-crime-miner
DBPORT=5432
DBPASSWORD=password`

## How to Replicate Via Docker

1. Open a terminal and move to the folder **'{project root}/video-crime-miner/**. You should find a dockerfile there.

2. Run the command **'docker build -t video-crime-miner .'** to build the image for the project.
    >*Note: the -t flag value is just for a title. You can name it whatever you want, of course.*

3. Run the command **'docker compose up'** to configure the Docker Image.

4. Navigate to the Docker Desktop application and view your images. You should find it built there. Click the **Run** button.

5. In the window that pops up, click **Optional settings** and fill in three required environment variables with the following names:
    >*REGION* is the AWS region you'll be accessing from
    >*AWS_ACCESS_KEY_ID* is the AWS access key to use their services
    >*AWS_SECRET_ACCESS_KEY* is the AWS secret access key to use their services

6. Click **Run** and your video-crime-miner is now containerized in Docker.

## Linting

1. Open a new terminal and move to the folder **{project root}/video-crime-miner/node-video-crime-miner/**

2. Execute command 'npm run lint', and your terminal should return any conflicts with the standard-with-typescript guide provided by the eslint module

## Rekognition

**How to recreate Rekognition service**

**I. Create an IAM administrator User**
    
**To enable IAM Identity Center**

1. Sign in to the AWS Management Console (https://console.aws.amazon.com/) as the account owner by choosing Root user and entering your AWS account email address. On the next page, enter your password.

2. Open the IAM Identity Center console (https://console.aws.amazon.com/singlesignon)

3. Under Enable IAM Identity Center, choose Enable.

4. IAM Identity Center requires AWS Organizations. If you haven't set up an organization, you must choose whether to have AWS create one for you. Choose Create AWS organization to complete this process.

    AWS Organizations automatically sends a verification email to the address that is associated with your management account. There might be a delay before you receive the verification email. Verify your email address within 24 hours.

**Create an administrative permission set**

1. Sign in to the AWS Management Console (https://console.aws.amazon.com/) as the account owner by choosing Root user and entering your AWS account email address. On the next page, enter your password
2. Open the IAM Identity Center console. (https://console.aws.amazon.com/singlesignon)
3. In the IAM Identity Center navigation pane, under Multi-account permissions, choose Permission sets.
4. Choose Create permission set.
5. For Step 1: Select permission set type, on the Select permission set type page, keep the default settings and choose Next. The default settings grant full access to AWS services and resources using the AdministratorAccess predefined permission set.
6. For Step 2: Specify permission set details, on the Specify permission set details page, keep the default settings and choose Next. The default setting limits your session to one hour.
7. For Step 3: Review and create, on the Review and create page, do the following:

    a. Review the permission set type and confirm that it is AdministratorAccess.

    b. Review the AWS managed policy and confirm that it is AdministratorAccess.

    c. Choose Create.

**Set up AWS account access for an administrative user**
1. Sign in to the AWS Management Console (https://console.aws.amazon.com/) as the account owner by choosing Root user and entering your AWS account email address. On the next page, enter your password.

2. Open the IAM Identity Center console (https://console.aws.amazon.com/singlesignon)

3. In the navigation pane, under Multi-account permissions, choose AWS accounts.

4. On the AWS accounts page, a tree view list of your organization appears. Select the check box next to the AWS account to which you want to assign administrative access. If you have multiple accounts in your organization, select the check box next to the management account.
5. Choose Assign users or groups.
6. For Step 1: Select users and groups, on the Assign users and groups to "AWS-account-name" page, do the following:

    a. On the Users tab, select the user to whom you want to grant administrative permissions.

    b. After you confirm that the correct user is selected, choose Next.
7. For Step 2: Select permission sets, on the Assign permission sets to "AWS-account-name" page, under Permission sets, select the AdministratorAccess permission set.
8. Choose Next. 
9. For Step 3: Review and Submit, on the Review and submit assignments to "AWS-account-name" page, do the following:

    a. Review the selected user and permission set.

    b. After you confirm that the correct user is assigned to the AdministratorAccess permission set, choose Submit.

**Sign in to the AWS access portal with your administrative credentials**
1. Sign in to the AWS Management Console (https://console.aws.amazon.com/) as the account owner by choosing Root user and entering your AWS account email address. On the next page, enter your password.

2. Open the IAM Identity Center console (https://console.aws.amazon.com/singlesignon)

3. In the navigation pane, choose Dashboard.

4. On the Dashboard page, under Settings summary, copy the AWS access portal URL.

5. Open a separate browser, paste the AWS access portal URL that you copied in Step 4, and press Enter.

6. Sign in by using either of the following:

    * sign in by using the user name that you specified when you created the user and the new password that you specified for the user. For more information, see Use the default directory and create a user in IAM Identity Center. (https://docs.aws.amazon.com/singlesignon/latest/userguide/get-started-use-identity-center-directory-create-user-in-identity-center.html)

7. After you are signed in, an AWS account icon appears in the portal.

8. When you select the AWS account icon, the account name, account ID, and email address associated with the account appear.

9. Choose the name of the account to display the AdministratorAccess permission set, and select the Management Console link to the right of AdministratorAccess.

    * When you sign in, the name of the permission set to which the user is assigned appears as an available role in the AWS access portal. Because you assigned this user to the AdministratorAccess permission set, the role will appear in the AWS access portal as: AdministratorAccess/username

10. If you are redirected to the AWS Management Console, you successfully finished setting up administrative access to the AWS account.

11. Switch to the browser that you used to sign into the AWS Management Console and set up IAM Identity Center, and sign out from your AWS account root user.

**II. Creating Service Role for SNS**

1. Open the IAM Identity Center console (https://console.aws.amazon.com/singlesignon)

2. Navigate to the Roles tab, under Access Management

3. Create a new Service Role using the JSON below:

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "sns:Publish"
            ],
            "Resource": "arn:aws:sns:*:*:AmazonRekognition*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "kinesis:PutRecord",
                "kinesis:PutRecords"
            ],
            "Resource": "arn:aws:kinesis:*:*:stream/AmazonRekognition*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "kinesisvideo:GetDataEndpoint",
                "kinesisvideo:GetMedia"
            ],
            "Resource": "*"
        }
    ]
}
```

4. After you are finished, take note of the arn of the service role

**III. Adding inline policy to IAM User**

1. Sign in to the AWS Management Console and open the IAM console at https://console.aws.amazon.com/iam/

2. In the navigation pane, choose Users

3. In the list, choose the name of the user to embed a policy in.

4. Choose the Permissions tab.

5. Choose Add permissions and then choose Add inline policy.

6. In the JSON tab, use the policy below:

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "MySid",
            "Effect": "Allow",
            "Action": "iam:PassRole",
            "Resource": "arn:Service role ARN created in previous section"
        }
    ]
}
```

