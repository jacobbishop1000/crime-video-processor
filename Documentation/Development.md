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
- PostgreSQL

## Technologies Needed

- NodeJS (npm) >= 19.0.0
- PostgreSQL >= 15.0

 
## Required IDEs, Frameworks

- No required IDE
- Need a terminal to use git, npm, psql

## Cloning project and initial configurations

1. In your terminal, move to desired folder location for the project. 
2. run **'git clone https://github.com/jacobbishop1000/video-crime-miner'**
3. move into the folder **'{project root}/video-crime-miner/node-video-crime-miner/'** and run **'npm run build'**
3. move into the folder **'{project root}/video-crime-miner/angular-video-crime-miner/'** and run **'npm run build-site'**

## Folder Structure

- **angular-video-crime-miner/**: contains configuration files for angular/typescript
    - **angular-video-crime-miner/node_modules/** contains node dependencies after npm install
    - **angular-video-crime-miner/src/**: source code for front-end site
        - **angular-video-crime-miner/src/app/**:  html, scss, and angular scripts for each of the site modules
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
- **node-video-crime-miner/.env
    - contains important environment variables that cannot be stored in source code

Jest Configuration
- **node-video-crime-miner/jest.config.js**
    - contains settings for jest test suite

## How to Test and Interpret the Results

1. Open a new terminal and move to the folder **{project root}/video-crime-miner/node-video-crime-miner/**

2. make sure to have run **'npm run build'** in this folder

3. run **'npm run test'** to run jest tests
    > if Jest gives errors, make sure your version of node is >= 19.0.0

4. The terminal output displays test results with visual aids (green check marks, red x's, etc.)

## Building a database

1. Open a new terminal and move to the folder **{project root}/video-crime-miner/node-video-crime-miner/postgre/**

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

3. Navigate to the Docker Desktop application and view your images. You should find it built there. Click the **Run** button.

4. In the window that pops up, click **Optional settings** and fill in three required environment variables with the following names:
    >*REGION* is the AWS region you'll be accessing from
    >*AWS_ACCESS_KEY_ID* is the AWS access key to use their services
    >*AWS_SECRET_ACCESS_KEY* is the AWS secret access key to use their services

5. Click **Run** and your video-crime-miner is now containerized in Docker.

## Linting

1. Open a new terminal and move to the folder **{project root}/video-crime-miner/node-video-crime-miner/**

2. Execute command 'npm run lint', and your terminal should return any conflicts with the standard-with-typescript guide provided by the eslint module