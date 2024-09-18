# Descriptive Data Analytic Platform (DAP) for the Vancouver Call Center

## Project Description
The Data Analytic Platform (DAP) for the Vancouver Call Center is a two-phase project aimed at enhancing the operational efficiency and safeguarding the data integrity of the city’s call center services. This project leverages advanced data analytics, cloud infrastructure, and AWS tools to improve service delivery, transparency, and compliance with data governance regulations.
## Objetive
### **Phase 1**: Call Handling Efficiency and Performance
In the first phase of the DAP, the primary goal was to improve call handling efficiency by analyzing operational metrics like call volume, average handling time, and service levels. By implementing a robust data pipeline using AWS services such as S3 for storage and AWS Glue for ETL processes, we processed call center metrics data (e.g., calls offered, calls handled). The descriptive metric introduced was the Call Handling Percentage, used to evaluate how efficiently the call center manages incoming calls, providing insights for resource planning and performance improvements​.
### **Phase 2**: Data Governance, Protection, and Monitoring
The second phase of the project focuses on safeguarding call center data while ensuring compliance with data governance and protection regulations​.This phase builds on the technical foundation laid in Phase 1 by integrating AWS's Well-Architected Framework, particularly focusing on the five pillars of operational excellence, security, reliability, performance efficiency, and cost optimization.
## Dataset
1. **Call Center Operational Data**
   - **dataset Name:** 3-1-1 Contact Center Metrics
   - **Source:** City of Vancouver’s open data portal.
   -  - **Details:** Includes metrics [Metrics](/images/Metrics_Files.png) such as total calls offered, calls handled, calls abandoned, average speed of answer, and service levels for the years 2023 and 2024.
2. **Call Handling Performance Data**
   - **dataset Name:** callsGeneral.xls 
   - **Source:** AWS S3 (Landing, Raw, Curated) [zones](/images/Zones.png). 
   - **Details:** Contains information such as the total number of calls offered, abandoned calls, and service level data​.   
3. **Handled Calls Data**
   - **dataset Name:** callsHandled.xls
   - **Source:** AWS S3
   - **Details:** Focuses specifically on handled calls, tracking successful interactions between call agents and customers.
4. **Sensitive Data Detection Logs**
   - **dataset Name:** AWS Glue ETL Data (callsGeneral raw)
   - **Source:** AWS Glue. ETL Data Pipeline Design, through [Data Linage diagram](/images/Linage.png) 
   - **Details:** Includes logs for sensitive data detection, such as PII, from call center records.
## Methodology
1. **Data Collection and Preparation:**
   - Load call center operational data from AWS S3, including callsGeneral.xls and callsHandled.xls, as well as other relevant data logs.
   - Use AWS Glue for data collection from different buckets and stages (landing, raw, curated)   
2. **Descriptive Statistics:**
3. **Data visualization:**
4. **Insights and Findings:**
5. **Recommendations:**
## Tools and Technologies
1. **Amazon S3 (Simple Storage Service)**
   - Used for storing raw, processed, and curated datasets. S3 was essential for organizing data in different zones (Landing, Raw, Curated) to manage the various stages of the ETL pipeline.
2. **AWS Gue**
   - AWS Glue was employed for **ETL (Extract, Transform, Load)** [processes](/images/Visual.png). It enabled automation of data cleaning, transformation, and schema modifications, especially through its visual interface and DataBrew
3. **AWS Glue DataBrew**
   - Used to clean, normalize, and structure [datasets](/images/Datasets.png) without writing code. It allowed the detection of PII (Personally Identifiable Information) and evaluation of data quality.
4. **Amazon Athena**
   - Enabled running **SQL queries** on data stored in S3, facilitating data analysis on large datasets. Athena was used to [manipulate](/images/Query.png) and analyze processed call center data​
5. **AWS CloudWatch**
   - Monitored AWS resources and applications, including alarms for billing, resource usage, and system health. CloudWatch was also used for real-time tracking of the performance and efficiency of the DAP.
6. **AWS CloudTrail**
   _ Tracked and logged **API calls** and user activity across AWS [resources](/images/Trail.png). It was critical for ensuring compliance, detecting unauthorized access, and auditing user actions.
7. **AWS Key Management Services (KMS)**
   - Provided encryption services to ensure that sensitive data was secured at rest and in transit. [KMS](/images/KMS_.png) was used for managing encryption keys and ensuring that data stored in S3 was encrypted.
8. **AWS Identity and Access Management (IAM)**
   - Managed access to AWS resources, ensuring that only authorized users and processes could interact with sensitive datasets. [IAM](/images/IAM.png) helped enforce the principle of least privilege.
9. **AWS EC2 (Elastic compute Cloud)**
   - Deployed virtual machines ([instances](/images/Instances.png)) to host applications and facilitate the sharing of reports. EC2 provided scalable compute resources for the DAP. 
10. **Draw.io**
    - Used to create and visualize data flow diagrams, architecture diagrams, and workflows for a better understanding of data processes and infrastructure.
## Deliverables
1. **Raw Data CSV Files**
   - Location: Stored in the [**raw**](/images/rawCSV.png) folder within the Amazon S3 bucket.
   - Description: This dataset includes unprocessed call center metrics directly ingested from the contact center logs. It serves as the initial input before any data cleaning or transformation occurs.
2. **Curated Data CSV Files**
   - Location: Stored in the [**curated**](/images/Curated.png) folder within the Amazon S3 bucket.
   - Description: These files represent the cleaned and transformed dataset, with personal identification information (PII) removed and quality issues resolved. The curated dataset is ready for analysis and querying.

3. **Trusted Data CSV Files**
   - Location: Stored in the [**Trusted**](/images/Trusted.png) folder within the Amazon S3 bucket.
   - Description: The final validated dataset, fully cleaned and processed, adhering to data governance and privacy policies. This dataset has been quality-checked and is ready for use in business intelligence (BI) tools or further analysis.

4. **documentation**
   - Location: Available in the repository as **markdown** files.
   - Description: Comprehensive documentation that includes descriptions of the data wrangling process, methodologies, transformations applied, and the AWS architecture used in the project.
  
