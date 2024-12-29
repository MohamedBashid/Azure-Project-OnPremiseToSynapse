### Azure-Project-OnPremiseToSynapse:

## Project Overview:  

This project demonstrates the design and implementation of an end-to-end data engineering pipeline to move data from an on-premise MySQL database to Azure Synapse Analytics for data transformation, storage, and visualization. The pipeline leverages several Azure services including Azure Data Factory, Azure Databricks, Azure Data Lake Gen2, and Power BI, providing a robust solution for scalable data integration and visualization.

The project involves extracting data from an on-premise MySQL server, transforming it through multiple layers (bronze, silver, and gold), and storing the final output in Azure Data Lake Gen2 in Delta Lake format. The data is then exposed to Azure Synapse Analytics for querying and analysis, with integration to Power BI for visualization and reporting.

## Key Features:

**Dynamic Data Extraction:** Uses Azure Data Factory pipelines to dynamically extract data from an on-premise MySQL database. \
**Delta Lake Transformation:** Raw data is transformed using Azure Databricks into structured, refined data stored in Delta Lake format. \
**Multi-layered Data Architecture:** Implements a bronze (raw), silver (transformed), and gold (curated) data architecture for optimized storage and performance. \
**Serverless Data Querying:** Utilizes serverless SQL pools in Azure Synapse Analytics to create views and query large datasets without managing infrastructure. \
**Power BI Integration:** Connects Azure Synapse to Power BI for seamless data visualization and real-time reporting.

## Architecture:

**1. Data Extraction:**

* Azure Data Factory: A dynamic pipeline is created in Azure Data Factory to automate the extraction of data from the on-premise MySQL server. The data is then copied into Azure Data Lake Gen2 in the bronze container as raw data.

**2. Data Transformation:**
   
* Azure Databricks: The raw data in the bronze container is ingested into Azure Databricks for transformation. This transformation process leverages Apache Spark to clean and refine the data. The transformed data is then saved in the silver container in Delta Lake format.
* Further data transformations are applied, and the cleaned and enriched data is moved to the gold container, also in Delta Lake format.

**3. Data Loading into Azure Synapse:**

* Azure Synapse Analytics: A serverless SQL pool is created to connect to the gold container. Views are defined for each table in the gold container to provide an easy way to query the data without needing to manage compute resources. A Synapse pipeline is used to automate the data loading and querying process.

**4. Power BI Visualization:**
   
* Power BI: Azure Synapse is connected to Power BI for real-time visualization. Power BI is used to create interactive reports and dashboards based on the views exposed through the Synapse Analytics serverless SQL pool.

## Technology Stack:

**Azure Data Factory:** Used for data extraction, pipeline orchestration, and movement of data from MySQL to Azure Data Lake. \
**Azure Databricks:** For data transformation using Apache Spark and Delta Lake format. \
**Azure Data Lake Gen2:** Storage solution for raw and transformed data (bronze, silver, and gold layers). \
**Azure Synapse Analytics:** Serverless SQL pools for querying and managing large datasets, along with pipelines for data orchestration. \
**Azure Key Vault:** To store the confidential information. \
**Power BI:** Data visualization tool used to connect with Synapse and present data in interactive reports and dashboards.

## Conclusion:

This project showcases an end-to-end data engineering solution on Azure, where data is seamlessly extracted from an on-premise MySQL database, transformed using Azure Databricks, and stored in Azure Data Lake Gen2 in a structured manner. The data is then queried via Azure Synapse Analytics and visualized in Power BI for actionable insights. The solution leverages Azure's scalable and serverless services, ensuring an efficient, automated pipeline that supports data-driven decision-making.



