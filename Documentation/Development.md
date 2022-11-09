# Development

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
 
## Required IDEs, Frameworks

- No required IDE
- Need a terminal to use git, npm

## Cloning project and initial configurations

1. In your terminal, move to desired folder location for the project. 
2. run **'git clone https://github.com/jacobbishop1000/video-crime-miner'**
3. move into the folder **'{project root}/video-crime-miner/node-video-crime-miner/'** and run **'npm install'**
3. move into the folder **'{project root}/video-crime-miner/angular-video-crime-miner/'** and run **'npm install'**

## Folder Structure

- **angular-video-crime-miner/**: contains configuration files for angular/typescript
    - **angular-video-crime-miner/node_modules/** contains node dependencies after npm install
    - **angular-video-crime-miner/out/** folder contains compiled code from TypeScript to JavaScript
    - **angular-video-crime-miner/src/**: source code for front-end site
        - **angular-video-crime-miner/src/app/**:  html, scss, and angular scripts for each of the site modules
- **node-video-crime-miner**: source code for aws node clients, also contains configuration files for node/typescript
    - **node-video-crime-miner/cli/**: simple command line interface to interact with files in s3 buckets and handle jobs from rekognition
    - **node-video-crime-miner/resources/**: contains a few sample files for testing uploads to s3 buckets and video analysis
    - **node-video-crime-miner/src/**:
        - **node-video-crime-miner/src/node/**: contains source code for creating and managing new clients for s3 and rekognition
        - **node-video-crime-miner/src/video/**: contains source code for connecting video object in s3 bucket to rekognition client, managing SNS messages and SQS queues for tracking progress on video analysis, and collecting report of detected labels
    - **node-video-crime-miner/test/**: contains the test files for s3, rekognition, sqs/sns client interaction
    - **node-video-crime-miner/node_modules/** contains node dependencies after npm install
    - **node-video-crime-miner/out/** folder contains compiled code from TypeScript to JavaScript

## Important config files

Node/Angular Configuration

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

Jest Configuration
- **node-video-crime-miner/jest.config.js**
    - contains settings for jest test suite

## How to Test and Interpret the Results

1. Open a new terminal and move to the folder **'{project root}/video-crime-miner/node-video-crime-miner/**

2. make sure to have run **'npm install'** in this folder

3. run **'npm test'** to run jest tests
    > if Jest gives errors, make sure your version of node is >= 19.0.0

4. The terminal output displays test results with visual aids (green check marks, red x's, etc.)