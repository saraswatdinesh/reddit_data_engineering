# reddit_data_engineering

It is sample data engineering project built with the intention to highlight and project how different technologies interact and integrate in a typical data engineering data pipeline. 

In a typical data engineering project we have to have the data source which in our case if reddit API, then the landing area where the data lands at our system, in our case local machine. 
Once we have the data in landing area, we process and publish the data to the staging after transformation. This transformed data as well the landing data is stored at some database or filesystem, in our case we decided to leverage AWS S3. 

Once we have the data in the transformed we can have an access layer or table for further analytics. In this project we leveraged both Amazon Redshift as well Glue crawler for building the tables and Athena for access the table using the SQL like syntax. 

Then this end to end system can be integrated with the any BI analytics tool such as looker, Tableau and PowerBI for further analytics and insights. 

Entire process flow was orchestrated leveraging the apache airflow and coded in python. ETL was completed in Pandas for local  and AWS Glue for cloud. 


**Solution Approach **

1. Create a virtual environment in Visual studio to ensure no dependencies go unnoticed.
2. Create a docker container to have the Apache airflow as an orchestration tool to help interact with the python code to execute the flow.
3. Configparser is used for parsing the configurations and help process the configurations
4. Once we had the setup we developed the ETL code called pipeline which is callable from DAG , airflow to establish a connection with reddit api and make a request for subreddit comments.
5. Once we have the data in the object we parse and load it to csv file leveraging pandas and numpy
6. Now as we have the data file we call the aws s3fs services to connect to the amazon S3 with the help of key values and connect to the S3 to upload the file.
7. Once we have the file on S3 we invoke a AWS glue job to execute and process the file uploaded in step 3 to make transform and load to another directory.
8. We then create a crawler to create a table for transformed data files. This is used for final analytics, with the help of Athena.
9. Also we can create Redshift table on the S3 object and access the data leveraging the power of redshift.


AWS S3 folder structure - 
