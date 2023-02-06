# Deployment

### Option 1: Install Using npm
 -run npm install node-video-crime-miner
 
 This allows the user to install the backend and use functions which can plugged into the rest of your project's code on an as-needed basis.

![Screenshot 2022-12-07 223555](https://user-images.githubusercontent.com/65315435/206350576-9fe13e97-5a9e-4be0-9879-f1bce354abb1.jpg)

#### Option 2: Starting the Angular Client

1. Move into **'{project root}/angular-video-crime-miner'** and run **'npm run start-site'**
2. After a moment of building, the site will be running. Any errors that occur at the time of building will appear in your terminal. Errors that could occur while the angular client is running may only be viewable by right clicking the background of the site, choosing **'Inspect'**, and navigating to the **'Console'**
3. Open a new terminal and move into **'{project root}/node-video-crime-miner'** and run **'npm run start'**
3. In your browser, go to **'localhost:4200/'**

#### Stopping the Angular Client/Express Server

 To stop the Angular Client or the Express Server, terminate the process as its running in your terminal

## Deploying local postgresql database
>*see Development.md for in depth walkthough of how to create and deploy the postgresql database*

#### Troubleshooting

- make sure that you have run **'npm install'** in both **'{project root}/angular-video-crime-miner'** and **'{project root}/node-video-crime-miner'**
- make sure that you are using *node >= 19*

### Dockerize the Application

- Setting up your .env file, you want to ensure that you have the PostgreSQL User name, password, and Database name.
our .env environment looks like this: 

#Isaac's awesome stuff!
AWS_BUCKET_REGION="us-east-1"
REKOG_BUCKET_NAME=video-crime-miner-video-test-bucket
AWS_ACCESS_KEY_ID="AKIA34RWTNEFV47IKRQW"
AWS_SECRET_ACCESS_KEY="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"
AWS_REKOG_REGION="us-east-1"
AWS_ROLE_ARN=arn:aws:iam::817232046347:role/RekogSNSRole
REGION="us-east-1"
NODE_PORT = 8000

#Database
DBHOST=localhost
DBUSER=postgres
DB=video-crime-miner
DBPORT=5432
DBPASSWORD=password

#postgresDB
POSTGRES_USER=root
POSTGRES_PASSWORD=password
POSTGRES_DB=video-crime-miner

#Angular
BASE_BACKEND_URL=http://localhost:8000/

- Setting up your Dockerfile:

#Angular Server
FROM node:19 AS angular-build
WORKDIR /usr/src/
COPY angular-video-crime-miner/ ./angular-video-crime-miner/
RUN cd angular-video-crime-miner && npm install @angular/cli && npm install && npm run build-site

#Node Server and Local Dev Fresh Clean Database
FROM node:19 AS node-client-build
WORKDIR /usr/src/
COPY node-video-crime-miner/ ./node-video-crime-miner/
RUN cd node-video-crime-miner && npm install && npm run build && npm run refresh

#Postgresql Server
FROM postgres:15 AS postgres-build
WORKDIR /usr/src/
COPY node-video-crime-miner/src/postgres/ /usr/src/video-crime-miner/node-video-crime-miner/src/postgres

EXPOSE 5432:8000

CMD ["node", "node-video-crime-miner/out/index.js"]

- Setting up your docker-compose.yml for PostgreSQL Database:

services:
  postgres:
    image: postgres:15
    healthcheck:
      test: ["CMD", "sh", "-c", "pg_isready -U $$POSTGRES_USER - e $$POSTGRES_PASSWORD=password -h $$(hostname -i)"]
      timeout: 45s
      interval: 10s
      retries: 10
    restart: always
    volumes:
      - ./db:/docker-entrypoint-initdb.d/
    ports:
      - "5432:8000"
    env_file: node-video-crime-miner/.env
