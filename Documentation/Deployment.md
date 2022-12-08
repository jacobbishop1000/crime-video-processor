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
