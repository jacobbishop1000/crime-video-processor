# Deployment

#### Starting the Angular Client

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