# 🚀 YouTube Data Engineering Project (AWS)

**A Data Engineering project that builds a robust, end-to-end pipeline to ingest and process YouTube trending data from Kaggle into AWS for dynamic analytics and insightful reporting.**  
*Inspired by Darshil Parmar’s YouTube Data Engineering Project – I followed his approach closely as my first data engineering project.*

---

## Overview

This project demonstrates an end-to-end data pipeline built on AWS that:
- **Ingests** raw CSV and JSON data (from Kaggle) into Amazon S3.
- **Transforms** the data using AWS Glue (with PySpark) by applying schema mappings, resolving data types, and cleaning nulls.
- **Automates** processes via AWS Lambda triggers.
- **Enables interactive querying** with AWS Athena.
- **Visualizes data** using Amazon QuickSight.


## AWS Services & Tools Used

- **Amazon S3:**  
  - Stores raw data files (CSV/JSON) and final cleaned data.
  - Organized using Hive-style partitions based on region.

- **AWS Glue:**  
  - Runs ETL jobs to read data from the Glue Data Catalog (pointing to S3), apply schema transformations (e.g., converting numeric fields to bigint), and write the output in Parquet format.
  - Utilizes DynamicFrames and ApplyMapping to structure the data.

- **AWS Lambda:**  
  - Automates specific tasks and triggers ETL jobs when new data arrives in S3.

- **AWS Athena:**  
  - Provides interactive SQL querying on the processed data stored in S3.

- **Amazon QuickSight:**  
  - Connects to Athena to create interactive dashboards and visualizations of YouTube trending metrics.

- **AWS CLI (via Windows CMD):**  
  - I used Windows CMD to execute AWS CLI commands.
  - A shell script (`s3_cli_command.sh`) is included to automate the upload of raw JSON and CSV files into S3 using the CLI.

- **PySpark:**  
  - Used within AWS Glue jobs to perform data transformation at scale.

---

## Project Goals

- **Data Ingestion:** Seamlessly load YouTube trending data from Kaggle into Amazon S3.
- **ETL Processing:** Clean and transform raw data into a structured format using AWS Glue.
- **Scalable Data Storage:** Organize data in S3 with proper partitioning for efficient querying.
- **Interactive Analytics:** Use AWS Athena and QuickSight to derive insights from the cleaned data.
- **Cloud-First Approach:** Leverage AWS services to process large-scale data beyond local capabilities.

---

## Repository Structure

- **README.md:**  
  - This documentation file.

- **architecture.jpeg:**  
  - Diagram illustrating the high-level architecture of the pipeline.

- **lambda_function.py:**  
  - AWS Lambda script used for triggering data processing tasks.

- **pyspark_code.py:**  
  - PySpark code for AWS Glue ETL jobs (data cleaning and transformation).

- **s3_cli_command.sh:**  
  - Shell script containing AWS CLI commands (run via Windows CMD) for copying raw JSON reference data and regional CSV files to S3.

---

## Getting Started

### **Prerequisites**
- An AWS account with appropriate permissions (S3, Glue, Lambda, Athena, QuickSight).
- AWS CLI installed (verified with `aws --version` in Windows CMD).
- Basic knowledge of PySpark and AWS services.

### **Steps to Run the Project**
1. **Upload Raw Data:**  
   Use the provided `s3_cli_command.sh` via Windows CMD to upload raw CSV and JSON files to your designated S3 bucket.
   
2. **Run the ETL Job:**  
   Deploy and run the AWS Glue job (using `pyspark_code.py`) to transform raw data and write cleaned data to S3.

3. **Trigger Lambda (Optional):**  
   Set up the AWS Lambda function (`lambda_function.py`) to automate data processing on new S3 uploads.

4. **Query Processed Data:**  
   Use AWS Athena to execute SQL queries on the cleaned data stored in S3.

5. **Visualize Insights:**  
   Connect Amazon QuickSight to Athena and create dashboards to analyze YouTube trending metrics.

---

## Credits & Inspiration

This project was [**inspired by Darshil Parmar’s YouTube Data Engineering Project**](https://youtu.be/yZKJFKu49Dk?si=NKSCNOtS_QJ9MlI-). I followed his approach word-for-word to learn the fundamentals of AWS data engineering. All credit goes to him, and I have built upon his work to showcase an end-to-end data pipeline.

---

## Future Enhancements

- **Enhanced ETL Optimization:** Improve performance with dynamic partitioning and incremental loads.
- **Real-Time Processing:** Integrate AWS Kinesis for streaming data ingestion.
- **Advanced Analytics:** Expand dashboards in QuickSight or incorporate additional BI tools.
- **Infrastructure as Code:** Use CloudFormation or Terraform to manage AWS resources.

---

## Contact

Feel free to reach out via [LinkedIn]([https://www.linkedin.com/in/yourprofile/)](https://www.linkedin.com/in/niraj-patil-linked/) or open an issue in this repository for questions or collaboration.

**Enjoy exploring the YouTube data pipeline on AWS!** 🚀
