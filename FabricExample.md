# Microsoft Fabric Pipeline Example

## 1. Base Extraction or Ingestion
* Trigger: By schedule if regular and significant changes, by metadata change if less frequent 
* Copy Data Activity: Pull raw file appropriate connector
* Lakehouse Storage: position in "Raw" folder or desired naming convention
* Validation Checks
  - If File DOES NOT Exist --> Create
  - If File DOES Exist --> Archive, Overwrite, or incremental append

## 2. Data Cleansing & Transformation with PySpark
* Data Flow Gen 2 with the Power Query editor is an option if preferred
* PySpark Cleaning (my general personal preference)
  - Null and Error Handling
  - Set to desired schema
* Set Format
  - Use Delta Parquet if continuing transformation and analysis within Fabric
  - Use desired format if client wants the data back at this stage
    + For instance, if excel, set the desired formatting for tables, frozen panes, etc.

## 3. Power BI or Continued Fabric
 * Delta Parquet table is set Lakehouse from previous step
 * Direct Lake engine automatically appends new data
 * Run Machine Learning Models (Random Forest etc.)
 * Distribute Delta Parquet Table for further client specific handling
   - Label appropriately and or place in designated folder containers
   - provide additional transformations as desired via pyspark 

## 4. Security, Presentation & Notifications
* Access Control & Security
  - Configure Workspace permissions
  - Apply Row-Level Security (RLS) rules as needed
* Sharing & Consumption
  - Share the updated links
  - Provide Direct Lake or semantic model access for self-service analysis
* Notification Activity
  - Send completion email notification
