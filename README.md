# Big Data Wrangling with Google Books Ngrams

This project involves processing and analyzing a dataset from the Google Books Ngrams using Apache Spark on AWS EMR. The objective is to demonstrate big data wrangling techniques and extract meaningful insights from the dataset.

## Project Structure

- `Mark_Benhaim_Unit_4_Big_Data_Wrangling_With_Google_Books_Ngrams_Part_1.ipynb`: Initial data processing and analysis steps.
- `Mark_Benhaim_Unit_4_Big_Data_Wrangling_With_Google_Books_Ngrams_Part_2_.ipynb`: Continued analysis including advanced data processing techniques.
- `Mark_Benhaim_Unit_4_Big_Data_Wrangling_With_Google_Books_Ngrams_Appendix_For_Steps.pdf`: Detailed steps and screenshots of the setup and execution process.

## Setup

### Requirements

- AWS Account
- Access to AWS EMR and S3 services
- SSH client installed on your local machine
- `.pem` key file for AWS access

### Initialization

1. **Create an EMR Cluster:**
   - Spin up a new EMR cluster on AWS with Apache Spark installed. Ensure that EMR notebooks are enabled for interactive analysis.

2. **Connect to EMR Cluster:**
   - Use SSH to connect to the head node of your cluster:
     ```bash
     ssh -i [path-to-your-pemkey].pem -L 9995:localhost:9443 hadoop@[Primary-node-public-DNS]
     ```
   - Replace `[path-to-your-pemkey]` and `[Primary-node-public-DNS]` with your specific details.

3. **Data Setup:**
   - Copy the Google Books Ngrams dataset from a public S3 bucket to the Hadoop Distributed File System (HDFS) on your EMR cluster:
     ```bash
     hadoop distcp s3://[bucket-name]/eng_1M_1gram.csv /user/hadoop/eng_1M_1gram/
     ```

### Running the Notebooks

- Access JupyterHub by navigating to `https://localhost:9995/` in your web browser.
- Log in with the default credentials (or those you have set up).
- Open the provided Jupyter notebooks to begin your analysis.

## Analysis Overview

The analysis consists of the following steps:

1. **Data Ingestion:**
   - Read data from HDFS into PySpark dataframes.

2. **Data Processing:**
   - Perform data cleaning, transformation, and aggregation operations.

3. **Data Export:**
   - Collect processed data and export it to your personal S3 bucket for persistence and further analysis.

4. **Insights and Visualization:**
   - Generate insights from the data using PySpark. Visualizations and results are presented within the Jupyter notebooks.

## Troubleshooting and Logs

- Ensure that your AWS permissions and network settings allow SSH and S3 access.
- Check EMR and Hadoop logs if you encounter issues during data processing steps.

For detailed step-by-step instructions including screenshots, refer to the `Mark_Benhaim_Unit_4_Big_Data_Wrangling_With_Google_Books_Ngrams_Appendix_For_Steps.pdf` document.

This README provides a clear guide for setting up and running your project, aimed at users familiar with AWS, EMR, and Jupyter notebooks. Adjustments might be needed based on specific configurations or updates to AWS services.

# License
This project is licensed under the [MIT License](LICENSE).

# Contact
For any inquiries or collaborations, please contact [Mark Benhaim](mbenhaim@umich.edu)

# Acknowledgments
Special thanks to Brainstation and Amazon
