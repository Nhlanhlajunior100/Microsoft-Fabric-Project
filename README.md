# Microsoft-Fabric-Project
This is a project built in Microsoft Fabric that implements the medallion architecture on the New York City Green Taxi public dataset. This portion of the project uses three PySpark(Python) notebooks to unzip, transform and load data from bronze to the silver layer of the medallion architecture. Microsoft Fabric Lakehouses were used for each layer of the medallion architecture.

A JSON file for the Microsoft Fabric pipeline has been included in the repository. The pipeline follows the following steps:
1. Uses the month lookup notebook to creates a delta table that lists the number of months present in an annual folder.
2. Passes the list of months to a ForEach iterator to use the Silver Transform and Load notebook to add transformations to each month's data and append that to a master delta table in the silver lakehouse.
3. Uses an Outlook activity to send an email to the team once the pipeline has successfully run. 
