# reddit_data_engineering

It is sample data engineering project built with the intention to highlight and project how different technologies interact and integrate in a typical data engineering data pipeline. 

We have leveraged docker for containerization to help install the dependencies, Airflow to control the flow of the data pipeline using DAG's, Python code to parse the configurations, connect with Reddit API to download the data to the local machine , pandas to parse the data and store the local file. 

The end goal is to push the local processing to aws and connect to aws to process it on the cloud along with it. 

This is mock up data pipeline which can be extended to included more complicated data processing and ingestion. 

Looking for your feedback on this.
