# User

## Itteration 1
1. In your terminal, navigate to **'{project-root}/node-video-crime-miner/src/cli/'** and run **'node main.js'**
2. This will launch a cli-application that will demo the following features:
    - Upload a video to s3 bucket
@@ -9,4 +10,11 @@
3. Choosing **'1. Upload'** will prompt the user for the file path to the video they would like to upload. If the file path is valid, it will upload the file to the bucket. You can now terminate the cli. 
4. Choosing **'2. Scan for faces'** will prompt the user for the name of a video in the s3 bucket. if there is an object with that name in the s3 bucket, an analysis will be done on the video and the terminal will print a report with data about any human faces detected in that video.
5. Choosing **'3. Scan for Labels'** will prompt the user for the name of a video in the s3 bucket. if there is an object with that name in the s3 bucket, an analysis will be done on the video and the terminal will print a report with data about any existing labels in Amazons dataset detected in that video. 
6. Choosing **'4. View files in s3 bucket'** will prompt the user for the name of an s3 bucket. If there is a bucket with the given name, the terminal will print a list of files found in the s3 bucket.
6. Choosing **'4. View files in s3 bucket'** will prompt the user for the name of an s3 bucket. If there is a bucket with the given name, the terminal will print a list of files found in the s3 bucket.

## Itteration 2
1. Open 2 terminals
2.Navigate to **\video-crime-miner\node-video-crime-miner** - run **npm run refresh**. In the adjacent terminal navigate to **\video-crime-miner\angular-video-crime-miner** and run **npm run refresh**.
3. Go to a browser and in the search bar enter **http://localhost:4200/**, this will take you to the main application dashboard.
![image](https://user-images.githubusercontent.com/87199787/206324847-72519bf9-1450-4c9c-a920-0df85bdcbc6e.png)
4. Head to the Box Icon on the left hand side to upload any searchable content!
5. once the page has loaded you can create a new case, adding a name, description and any tags you may want. 
6. if you go to the "Upload Files" tab, you have the option to add files from  your system to upload to our database.
7. Head to the Icon that looks like a tag, once there it should show you a list of any cases you may have.
