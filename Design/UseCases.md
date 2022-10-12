## Actors

* Law Enforcement Officer
    * Officer who is investigating a case and has too much video evidence to manually consume and scrape for important information

## Use Cases

* UC1 - Login
    * Actor: **Law Enforcement Officer**
    * An officer will have a password protected account associated with their past and onging cases, along with their uploaded files and reports.

* UC2 - Create new case
    * Actor: **Law Enforcement Officer**
    * An law enforcement officer is likely going to be working on multiple cases, and you may not want to have something that resembles a single folder with every file from every case that they are working or ever had worked on. For this reason, the UI will divide the files, terms, and reports by each case that the officer is working on. 

* UC3 - Upload File to case
    * Actor: **Law Enforcement Officer**
    * An officer working on a case may have video footage they wish to create a report for in a case. For this, they must upload a file containing the data of this footage for the software to use create a report out of. 

* UC4 - Create report from key terms and uploaded files
    * Actor: **Law Enforcement Officer**
    * The current purpose of the software we will be working on is to create transcripts from audio and video files, and search for key terms in speech. The feature we will be adding will be searching for key objects in video data.
    * The software then analyzes each frame of an uploaded video file to identify key objects and events, record the number of triggered events and associates timestamps with these events for the user to review in an organized report. 



 
