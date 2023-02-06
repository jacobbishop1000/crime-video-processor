# User

## Iteration 1
1. In your terminal, navigate to **'{project-root}/node-video-crime-miner/src/cli/'** and run **'node main.js'**
2. This will launch a cli-application that will demo the following features:
    - Upload a video to s3 bucket
@@ -9,4 +10,11 @@
3. Choosing **'1. Upload'** will prompt the user for the file path to the video they would like to upload. If the file path is valid, it will upload the file to the bucket. You can now terminate the cli. 
4. Choosing **'2. Scan for faces'** will prompt the user for the name of a video in the s3 bucket. if there is an object with that name in the s3 bucket, an analysis will be done on the video and the terminal will print a report with data about any human faces detected in that video.
5. Choosing **'3. Scan for Labels'** will prompt the user for the name of a video in the s3 bucket. if there is an object with that name in the s3 bucket, an analysis will be done on the video and the terminal will print a report with data about any existing labels in Amazons dataset detected in that video. 
6. Choosing **'4. View files in s3 bucket'** will prompt the user for the name of an s3 bucket. If there is a bucket with the given name, the terminal will print a list of files found in the s3 bucket.
6. Choosing **'4. View files in s3 bucket'** will prompt the user for the name of an s3 bucket. If there is a bucket with the given name, the terminal will print a list of files found in the s3 bucket.

## Iteration 2
1. Open 2 terminals
2.Navigate to **\video-crime-miner\node-video-crime-miner** - run **npm run refresh**. In the adjacent terminal navigate to **\video-crime-miner\angular-video-crime-miner** and run **npm run start-site**.
3. Go to a browser and in the search bar enter **http://localhost:4200/**, this will take you to the main application dashboard.
![image](https://user-images.githubusercontent.com/87199787/206324847-72519bf9-1450-4c9c-a920-0df85bdcbc6e.png)
4. Head to the Box Icon on the left hand side to upload any searchable content!
![image](https://user-images.githubusercontent.com/87199787/206339160-672e41c7-f34b-4f55-9b9c-c90bf54e15c3.png)
5. once the page has loaded you can create a new case, adding a name, description and any tags you may want. 
![image](https://user-images.githubusercontent.com/87199787/206339284-58db31e7-09c8-4c37-a97b-79e8723a158a.png)
6. if you go to the "Upload Files" tab, you have the option to add files from  your system to upload to our database.
![image](https://user-images.githubusercontent.com/87199787/206339367-33c6deae-f142-48d7-a8d0-68b81fcf0020.png)
7. Head to the Icon that looks like a tag, once there it should show you a list of any cases you may have.
![image](https://user-images.githubusercontent.com/87199787/206339452-03a9286c-7067-4180-b208-bb7ba60dadf9.png
![image](https://user-images.githubusercontent.com/87199787/206340854-f01df8eb-ce06-4ae6-88e0-9f68631436f9.png)

## Iteration 3
1. Open 2 terminals
2. Navigate to **\video-crime-miner\node-video-crime-miner** - run **npm run refresh**. In the adjacent terminal navigate to **\video-crime-miner\angular-video-crime-miner** and run **npm run start-site**.
3. Go to a browser and in the search bar enter **http://localhost:4200/**, this will take you to the main application dashboard.
![image1](https://user-images.githubusercontent.com/83672002/217040365-b4b96ff8-5c21-416a-b106-59fc0e430ff6.png)

4. Click on the side-nav bar to see options for other pages to view, and click on 'New Case'
![image2](https://user-images.githubusercontent.com/83672002/217040901-c279ea1c-cfcc-4f25-8889-553d0e96ca5b.png)
5. Enter in a name for your case, and a brief description. Example: CASE NAME: TEST CASE, CASE DESCRIPTION: A Test Case. Click on 'SUBMIT A NEW CASE'.
6. Now return to the side-nav bar and click 'View/Edit Case' to go to the next page.
![image3](https://user-images.githubusercontent.com/83672002/217043760-247d64e4-465d-4ad6-b0c8-16e51fcf4576.png)
7. Select a case by clicking on one of the hyperlinks in the table, like 'TEST CASE' for example
![image4](https://user-images.githubusercontent.com/83672002/217044882-78f68274-29d0-41ec-8d31-a8604234ca9f.png)
8. Click on the button labeled 'Browse...', and select a .mp4 video file to upload. For this walkthrough, We will select 'attempted_robbery.mp4'
![image5](https://user-images.githubusercontent.com/83672002/217045508-ddcac34c-9be8-4b7b-8296-e5a8513aef95.png)
9 After selecting your file and clicking 'UPLOAD', wait for the page to refresh in a few seconds, and you should see the file included in your 'Related Files' section, which a hyperlink labled 'Start New Label Detection'. Click on that.
![image6](https://user-images.githubusercontent.com/83672002/217046152-ad238b62-a69d-4ab0-adae-e156efa858dc.png)
10. On this page, you will be able to add tags to your job. Enter a phrase to search for in your video, like 'Person'. After you see your tag included in the 'Verify and Submit' section, you can click the 'SUBMIT' button to start the process of detecting labels in a video. After clicking 'Submit', click on 'Back to Case' in the top left corner.
![image7](https://user-images.githubusercontent.com/83672002/217047355-06198120-c079-4eab-8bd1-6f949b6397d0.png)
11. Back on the previous 'DETAILED CASE INFORMATION' page, if you scroll down to the bottom, you should see a newly populated table row in the 'Outputs Run' section, whith the last column having a hyperlink labeled 'View Results'. Click on this to view the results of the label detection job ( It may take a moment for the job to finish in the background, so if no results come up when they were expected, try refreshing your page.  )
![image8](https://user-images.githubusercontent.com/83672002/217048609-15b5bb41-0b12-4796-b16b-1bb019c8da29.png)
12. The next page will display the results of the label detection in a table titled 'Label Detection Results'. Clicking on the buttons in the 'Timestamp in Milliseconds' column will seek that timestamp in the video being displayed in the video player, and draw a border around the object associated with the detection
![image9](https://user-images.githubusercontent.com/83672002/217049749-f132b7b1-ceb9-410c-8793-74c41e1f6238.png)

Picture below is the video player when the page initially loads
![image10](https://user-images.githubusercontent.com/83672002/217050079-1c38ac2a-4cc6-47d1-a05a-a68205a5ac32.png)

Picture below is the video player after clicking on the first detected label's timestamp, which matches the tag we chose in Step 10, 'Person'. Clicking on a new timestamp will seek out that timestamp in the video, delete any old borders present on the video player, and place a border for the detection selected. 
![image11](https://user-images.githubusercontent.com/83672002/217050640-c59f1d4c-437a-425b-8949-0c4f61daed6e.png)







