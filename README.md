# 🚖 CodTech Internship — Task 1: Big Data Analysis

This repository contains the first task for the CodTech IT Solutions internship. The objective is to perform scalable exploratory data analysis (EDA) on a large dataset to extract meaningful insights.

## 📊 Project Overview
* **Tool Used:** **Dask** (optimized for scalable parallel computing)
* **Dataset:** NYC Yellow Taxi Trip Data (comprising over 12 million records)
* **Target File:** `yellow_tripdata_2015-01.csv`

---

## 🚀 Key Features of the Analysis
The analysis is structured systematically in the Jupyter notebook:

1. **Scalable Data Loading**: Demonstrates lazy loading using Dask DataFrames, showing how to handle data that exceeds standard RAM capacities.
2. **Exploratory Data Analysis (EDA)**:
   * Verification of total record count (12.7+ million rows).
   * Statistical summary of fare amounts, trip distances, and passenger counts.
   * Assessment of missing data values.
3. **Data Cleaning & Filtering**:
   * Filtering out invalid/negative fare amounts and distances.
   * Handling outlier values to ensure accurate insights.
4. **Insights Derived**:
   * Analysis of passenger count distributions.
   * Correlation between trip distance and total fare amount.
   * Distribution of payment types and tip habits.

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
