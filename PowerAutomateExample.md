# Power Automate Example

## Receive Scheduled Report Email with Attachment 
* One Drive for Business
* Get Name and Contents
* Condition
  - If File Does NOT Exist --> Create...
  - If File DOES Exist --> Update...
* Send to Storage --> Sharepoint/OneDrive/PC/Cloud/etc
* Run Python Cleaning Script
  - Null and Error Handling
  - Align for desired Schema
  - Set format (example from csv to Excel if needed)
  - Set particular formatting adjustments (table, frozen panes, headers, etc)
* Set for Presentation / Consumption
  - If client desired an Excel, commit to the excel formatting as desired
  - If client desired PowerBI or similar, ensure in the "Folder Level" for PowerBI data processing
     + This allows for all files in the folder with the exact same schema to be processed and combined together
  - Provide access via links or as desired
     + set appropriate permissions and or row level access
     + send verification email notifications
