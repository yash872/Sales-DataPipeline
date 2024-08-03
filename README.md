# Sales-DataPipeline
***
## Project Overview
This project is an overview of an e-commerce data pipeline that involves building a sophisticated event-driven data ingestion and transformation pipeline focusing on e-commerce transactional data.
We will design a system using AWS services such as S3, Lambda, Glue, Redshift, and SNS to ingest, transform, validate, and upsert data into Amazon Redshift for analytical purposes.
***


## Architectural Diagram
![Architecture Design](https://github.com/yash872/E-Commerce-DataPipeline/blob/main/Images/E-CommerceDataPipeline.png)

***

## Key Steps
### 1. Create a Table "OrdersRawTable" in DynamoDB
![DynamoDB_Table](https://github.com/yash872/Sales-DataPipeline/blob/main/Images/DynamoDB_Table.JPG)

### 2. Create a Data Stream "kinesis-for-sales-data" in Kinesis.
![KinesisDataStream](https://github.com/yash872/Sales-DataPipeline/blob/main/Images/KinesisDataStream.JPG)

### 3. Create a Event Bridge Pipe to ingest data from DynamoDb Stream to Kinesis Stream.
![EventBridge](https://github.com/yash872/Sales-DataPipeline/blob/main/Images/EventBridge.JPG)

- Note: Give the attached IAM role the permission to access DynamoDB & Kinesis
    - AmazonDynamoDBFullAccess
    - AmazonKinesisFullAccess

### 4. Run the Mock data generator script to load the data in DyanomoDB.
![DataLoadCMD](https://github.com/yash872/Sales-DataPipeline/blob/main/Images/DataLoadCMD.JPG)

### 4. Check the Data Load
- Data should be visible in DynamoDB Table "OrdersRawTable"
![DynamoDB_DataLoad](https://github.com/yash872/Sales-DataPipeline/blob/main/Images/DynamoDB_DataLoad.JPG)

- Event Bridge should be triggerd and data should flow from DyanomoDB Stream to Kinesis Stream
![KinesisDataLoad](https://github.com/yash872/Sales-DataPipeline/blob/main/Images/KinesisDataLoad.JPG)

### 4. Check the Change Data Capture (CDC) Events
- Before Edit the data
    ![before1](https://github.com/yash872/Sales-DataPipeline/blob/main/Images/before1.JPG)
    ![before2](https://github.com/yash872/Sales-DataPipeline/blob/main/Images/before2.JPG)
 
- After Edit the data
    ![after1](https://github.com/yash872/Sales-DataPipeline/blob/main/Images/after1.JPG)
    ![after2](https://github.com/yash872/Sales-DataPipeline/blob/main/Images/after2.JPG)
    ![after3](https://github.com/yash872/Sales-DataPipeline/blob/main/Images/after3.JPG)

