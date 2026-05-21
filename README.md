# 🚖 CodTech Internship — Task 1: Big Data Analysis

## 👥 Intern Profile
* **Company:** CODTECH IT SOLUTION
* **Name:** DEVENDRA KAGE
* **Intern ID:** CTIS9127
* **Domain:** DATA ANALYSIS
* **Duration:** 4 weeks (May 2026)
* **Mentor:** NEELA SANTOSH

---

## 📊 Project Overview
* **Tool Used:** **Dask** (optimized for scalable parallel computing)
* **Dataset:** NYC Yellow Taxi Trip Data (comprising over 12 million records)
* **Target File:** `yellow_tripdata_2015-01.csv`

---

## 📝 Detailed Task Description
As part of the CodTech IT Solutions Data Analysis Internship, this project addresses one of the fundamental challenges in modern data science: processing and analyzing datasets that exceed the memory capacity of standard local machines. Conventional data analysis libraries, most notably pandas, load the entire dataset directly into the computer's Random Access Memory (RAM). When working with files that span millions of records and gigabytes of disk space, this approach frequently leads to Out-Of-Memory (OOM) crashes and CPU bottlenecks due to single-threaded execution.

To solve this bottleneck and demonstrate true scalability, this task utilizes **Dask**, a flexible library for parallel computing in Python. Dask is designed to scale analytics from single-core laptops to multi-node clusters. For this analysis, we used the **NYC Yellow Taxi Trip Data from January 2015**, an exceptionally large dataset containing over **12.7 million records** and 19 columns. Managing such a vast amount of geographical, financial, and temporal information requires efficient data ingestion and computational workflows.

The project is structured into several distinct phases:
1. **Lazy Loading and Ingestion**: Using `dask.dataframe.read_csv`, the dataset is ingested lazily. Unlike pandas, which executes operations immediately, Dask builds a task graph (DAG - Directed Acyclic Graph) of the operations. The dataset is divided into 31 partitions, allowing Dask to stream and process chunks of the CSV in parallel without loading the full 12+ million rows into RAM at once.
2. **Exploratory Data Analysis (EDA)**: Initial explorations verify the shape of the dataset (12,748,986 rows and 19 columns) and examine the schema. Dask's parallel computation is used to count total rows, inspect column data types (such as pyarrow strings for datetimes), and search for missing data (discovering minimal missing values in the improvement surcharge column).
3. **Data Cleaning**: Raw taxi logs contain anomalies and bad data, such as negative fare amounts, trips with zero distance, or passenger counts of zero. Using boolean filtering, these erroneous entries are pruned. This phase removed approximately 90,581 erroneous records, leaving a clean dataset of 12,658,405 rows for final analysis.
4. **Insight Extraction via Parallel Aggregations**:
   * *Financial Averages*: Computation of the overall average fare ($11.91), average tip ($1.85), average trip distance (13.46 miles), and average total amount ($15.10).
   * *Demographics*: Grouping trips by passenger count to understand the distribution of single vs. multi-passenger trips.
   * *Payment Analysis*: Grouping and calculating average fare by payment type (Credit Card vs. Cash vs. Dispute), which revealed that credit card payments carry an average fare of $12.41 compared to cash payments at $10.97.
   * *Tip Percentage*: Evaluating tipping behavior, indicating that passengers tip an average of 14.83% of the base fare.
   * *Vendor Performance*: Segmenting data between taxi vendors (CMT vs. VTS) to analyze relative performance metrics.
5. **Data Visualization**: Staging aggregated outputs to pandas for plotting. Visual representations include passenger count distributions, correlation plots of fare vs. distance, and bar charts of average fares across different payment methods.

By utilizing Dask's lazy evaluation, partition-level processing, and parallelized groupby operations, this project demonstrates how data analysts can efficiently scale their workflows to manage big data on consumer-grade hardware.

---

## 🛠️ How to Run Locally

### Prerequisites
Make sure you have Python installed on your system. It is recommended to use a virtual environment.

### Setup Instructions
1. **Clone the repository**:
   ```bash
   git clone https://github.com/dvk12006-code/dev1927.git
   cd dev1927
   ```

2. **Install the required packages**:
   ```bash
   pip install dask[complete] pandas numpy matplotlib seaborn jupyter
   ```

3. **Get the Dataset**:
   * Download the dataset from Kaggle or other NYC Taxi sources.
   * Place the `yellow_tripdata_2015-01.csv` in your working directory.

4. **Launch the Notebook**:
   ```bash
   jupyter notebook
   ```
   Open `task1_big_data_analysis.ipynb` and run the cells.
