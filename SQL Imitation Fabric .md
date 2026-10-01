# Microsoft SQL Server Imitation Fabric
Apply Medallion Architecture common to Fabric using a SQL Instance.


## Base Extraction or Ingestion Into BronzeDB
* Establish Link Server for source servers into target 
* SQL Agent Job schedule pulling Data from source to BronzeDB  
  - Although not always expressed, it is my recommendation to limit ingestion  
  - And perform basic cleaning and transormations
* Use either Drop Table or Truncate Table methods depending on situation

## Thorough Cleansing & Transformation with SQL to SilverDB
* Build SQL script transformations on BronzeDB tables as desired  
  - Format tables to be ready for experienced or professional consumption
* SQL Agent Job schedule Transforming Data from BronzeDB to SilverDB  
* Use either Drop Table or Truncate Table methods depending on situation
* In many cases reporting at this state is sufficient
  -PowerBI and SSRS, etc. can now happily and easily use SELECT (*) on SilverDB.schema.table

## Finalization for Presentation into GoldDB
* Build SQL script transformations on BronzeDB and or SilverDB tables as desired  
  - Format tables to be ready for end-user or presentation consumption
* SQL Agent Job schedule Transforming Data from BronzeDB and or SilverDB into GoldDB  
* Use either Drop Table or Truncate Table methods depending on situation
* Reporting at this stage should be easy for almost any skill level
  - PowerBI and SSRS, etc. can readily use SELECT (*) on GoldDB.schema.table  
  - Power Automate or Python extractions should easily produce a desired report
