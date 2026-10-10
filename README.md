# Yuva Intern – Week 2: Data Preprocessing

## 📌 Project Overview

This repository contains the work completed for **Week 2 of my Junior Data Scientist Internship at Yuva Intern**, focused on data preprocessing using Python.

The project uses a publicly available paneer storage study dataset to demonstrate data cleaning, missing-value analysis, outlier detection, and feature standardization.

The objective is to transform raw food-processing data into a clean, structured format suitable for further exploratory data analysis and future machine learning workflows.

## 🎯 Objectives

- Load and inspect raw food-processing datasets.
- Identify and handle missing values appropriately.
- Remove unnecessary header rows, summary rows, and blank rows.
- Standardize column names and data formats.
- Validate microbial logarithmic measurements.
- Detect potential outliers using the Interquartile Range (IQR) method.
- Standardize selected numerical features using `StandardScaler`.
- Export cleaned and analysis-ready datasets.

## 📊 Dataset Information

**Dataset title:** Storage study data for paneer in controlled RH and Temperature environment

**Source:** Mendeley Data  
**DOI:** [10.17632/rd9dmr54xx.2](https://doi.org/10.17632/rd9dmr54xx.2)  
**Licence:** CC BY 4.0

The dataset contains paneer storage observations, including microbial measurements, physicochemical properties, and sensory attributes.

### Data characteristics

- 70 observations
- 14 storage days (Day 0–Day 13)
- 5 replicates per day
- 24 columns in the cleaned dataset

## 🛠️ Tools and Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

## 🔍 Preprocessing Workflow

### 1. Data Inspection
- Loaded the source data.
- Examined dataset dimensions, column names, data types, and missing values.
- Identified unnecessary header rows, summary statistics, and blank rows.

### 2. Data Cleaning
- Removed non-observation rows.
- Standardized column names.
- Retained the 70 actual observations.
- Preserved meaningful missing values rather than inventing replacement values.

### 3. Missing-Value Analysis
Missing values were examined across microbial, sensory, and production-related variables.

Microbial logarithmic measurements may be undefined when the corresponding count is zero. These cases were retained rather than assigning arbitrary values.

### 4. Logarithmic Value Validation
Existing microbial logarithmic measurements were checked against the formula:

`Log10 Count = log10(CFU count × 10^dilution)`

Comparable records were validated against the calculated values.

### 5. Outlier Detection
The Interquartile Range (IQR) method was used to identify potential outliers.

Potential outliers were retained because unusual observations should not be removed automatically without further investigation.

### 6. Feature Standardization
Selected numerical features were standardized using Scikit-learn's `StandardScaler`.

Standardization helps put numerical variables on comparable scales for suitable downstream analytical and machine learning workflows.

## 📁 Repository Structure

```text
yuva-intern-week2-data-preprocessing/
├── data/
│   └── processed/
│       ├── paneer_cleaned_data.csv
│       ├── paneer_analysis_data.csv
│       └── paneer_scaled_data.csv
├── notebooks/
│   └── 02_data_preprocessing.ipynb
├── report/
│   └── Week_2_Data_Preprocessing_Report.docx
└── README.md
