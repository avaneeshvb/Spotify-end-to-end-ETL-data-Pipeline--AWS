# Spotify Music Data ETL Pipeline Using AWS

## Overview
This project demonstrates a scalable and automated ETL pipeline built to extract, transform, and load music data from Spotify, utilizing a suite of AWS services including Lambda, S3, Glue, Athena, and CloudWatch. Designed for the music industry, this pipeline streamlines data processing, delivering valuable insights through an efficient, serverless architecture.

## Data Flow Overview
The pipeline starts by fetching raw music data from Spotify’s API, processes it using AWS Lambda for data extraction and transformation, and stores the results in Amazon S3. AWS Glue catalogs the data, while Athena enables querying for analysis.

![ETL Pipeline Architecture](https://github.com/avaneeshvb/Spotify-end-to-end-ETL-data-Pipeline--AWS/blob/main/Spotify%20end%20to%20end%20DE.png)

### 1. Extract (Spotify API via AWS Lambda)
- **Spotify API**: The pipeline begins by pulling data (tracks, artists, albums, etc.) from Spotify using a Python script within an AWS Lambda function.
- **Amazon CloudWatch**: CloudWatch triggers this Lambda function daily to ensure timely data updates.

### 2. Load Raw Data (S3 Bucket)
- **Amazon S3 (Raw Data)**: The extracted data is stored securely in an Amazon S3 bucket, providing scalable storage for raw data.
- **Trigger (Object Put)**: When new raw data is uploaded to S3, an event trigger automatically kicks off the next stage of the pipeline.

### 3. Transform (Data Processing via AWS Lambda)
- **AWS Lambda (Transformation)**: A second Lambda function processes the raw data by cleaning, formatting, and aggregating it, preparing it for storage.
- **Amazon S3 (Transformed Data)**: The transformed data is stored separately in another S3 bucket for ease of access and independent management.

### 4. Catalog Data (AWS Glue)
- **AWS Glue Crawler**: AWS Glue automatically scans the transformed data in S3, inferring its schema and creating a catalog that simplifies data discovery.
- **AWS Glue Data Catalog**: The catalog metadata is stored centrally, making querying and analytics easier.

### 5. Analyze Data (Amazon Athena)
- **Amazon Athena**: Using Athena, you can run SQL queries directly on the data stored in S3, allowing real-time analysis and insights.

## Key Benefits
- **Fully Automated Workflow**: Using CloudWatch, Lambda, and S3 event triggers, the pipeline runs automatically with daily updates, requiring minimal manual oversight.
- **Scalable and Secure Storage**: Amazon S3 ensures seamless scalability for storing both raw and processed data, making it suitable for large datasets.
- **Serverless and Cost-Efficient Processing**: AWS Lambda handles both extraction and transformation, keeping the architecture serverless and reducing infrastructure costs.
- **Automated Data Discovery**: AWS Glue simplifies metadata management by automatically cataloging data, making it easy to access and analyze.
- **Real-Time Insights**: With Athena, users can instantly query the data for actionable insights, improving decision-making in the music industry.

## Conclusion
This project, completed as part of the Python for Data Engineering course by Data Vidya, showcases how AWS services can be effectively combined to build a robust, automated ETL pipeline. This pipeline allows for real-time analysis of music data, providing invaluable insights to stakeholders in the music industry.
