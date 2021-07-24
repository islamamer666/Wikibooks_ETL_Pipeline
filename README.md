# **Wikibooks ETL Pipeline**
An end-to-end ETL Pipeline for Building Data Warehouse and Analytics Platform
## **Table of Contents**
* [Architecture Diagram].
* [How it works]
* [References]
* [License]

### **Architecture Diagram**


![architecture](https://user-images.githubusercontent.com/72258715/126880156-9641253f-3f1f-40c8-96d7-3e88b7e2268e.png)
**ETL Flow**
* Data is captured by python wrapper from Kaggle API
* Data collected from the API is uploaded to landing zone Amazon s3 bucket
* Then data is moved to working zone
* Then spark job is triggered which reeds data from working zone and apply transformations and moved data to the processed zone
* Then data moved to Redshift staging tables
*  UPSERT operation is performed on the Data Warehouse tables to update the dataset
*  ETL job execution is completed once the Data Warehouse is updated
*  Airflow DAG is used to schedule and orchestrate job tasks


#### **Reference**


##### **License**
Distributed under the MIT License
