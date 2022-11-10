# User

1. In your terminal, navigate to **'{project-root}/node-video-crime-miner/src/cli/'** and run **'node main.js'**
2. This will launch a cli-application that will demo the following features:
    - Upload a video to s3 bucket
    - detect faces in a video
    - detect labels in a video
    - view files in s3 bucket
3. Choosing **'1. Upload'** will prompt the user for the file path to the video they would like to upload. If the file path is valid, it will upload the file to the bucket. You can now terminate the cli. 
4. Choosing **'2. Scan for faces'** will prompt the user for the name of a video in the s3 bucket. if there is an object with that name in the s3 bucket, an analysis will be done on the video and the terminal will print a report with data about any human faces detected in that video.
5. Choosing **'3. Scan for Labels'** will prompt the user for the name of a video in the s3 bucket. if there is an object with that name in the s3 bucket, an analysis will be done on the video and the terminal will print a report with data about any existing labels in Amazons dataset detected in that video. 
6. Choosing **'4. View files in s3 bucket'** will prompt the user for the name of an s3 bucket. If there is a bucket with the given name, the terminal will print a list of files found in the s3 bucket.