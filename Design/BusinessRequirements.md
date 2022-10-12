
    Prepare a document under the Design folder of your main GitHub repository called BusinessRequirements.md
    Have a proper, readable markdown formatting in the document.
    
        Check https://www.markdowntutorial.com/Links to an external site. for inspiration (or search for one yourself).
    This document will have a header called Business Requirements.
    
    The remaining of the content will be the business requirements, each in one bullet point with:
        An ID such as BR1, BR2, etc for each business requirement to refer later in other documents.
        One paragraph of explanation why do you think this is one of the business requirements.
        
    Check the Business analyst and establishing the business requirements slides and notes again to remind your team what a business requirement is.
    Find the core business requirements.
        Check the Previously in CS495/498 slides and notes for a hands-on business requirement exercise on a real project.
        Communicate with your client to clarify if you are not sure.
        Communicate with your mentor to clarify if you are not sure.
        
    Submit a link to BusinessRequirements.md file.
        Your submission should be something like: https://github.com/{teamMemberName}/{projectName}/blob/master/Design/BusinessRequirements.md
        
# Business Requirements
## Chuqlabs CrimeMiner: Video Processor
### Summary:
Chuqlabs CrimeMiner is a Evidence transcription service.

### Project Scope
the Video Processor(VP), given a video or multiple video files, sort through and discover evidence based on labels given to search. 
Each correlation having a percentage certainty. 

### Non-Functional Requirements:
- The Video Processor(VP) should be able to account for Color and non-color video.
- The VP should account for different resolutions.
- The VP should account for different image ratio's.
- The VP should be able to handle multiple video formats.
- The VP should be able to take large files.
- The VP should be able to handle folders with multiple video files.

### Functional Requirements:
- The Video Processor(VP) should be able to locate a given label
- The VP should be able to use important meta variables for data gathering, such as location.
- The VP should be able to trace the path of an individual giving percentage certainty.
- The VP should be able to trace the path of a vehicle giving percentage certainty.
- The VP should be able to mark every occurance of a label giving percentage certainty.
- 
