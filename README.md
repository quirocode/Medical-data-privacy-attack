# Healthcare Data Privacy Analysis: Breaking Anonymization with Google Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/quirocode/Medical-data-privacy-attack/blob/main/notebooks/linkage_attack_analysis.ipynb)
[![Python](https://img.shields.io/badge/Python-3.12-blue?style=flat-square&logo=python)](https://www.python.org/)
[![Google Colab](https://img.shields.io/badge/Google%20Colab-Data%20Analysis-orange?style=flat-square&logo=googlecolab)](https://colab.research.google.com/)
[![Kaggle API](https://img.shields.io/badge/Kaggle-Dataset%20Source-blue?style=flat-square&logo=kaggle)](https://www.kaggle.com/)

## About Me & Project Purpose
Hi! I am an enthusiastic Data Analytics student passionate about turning massive, complex datasets into meaningful insights. In the healthcare sector, data is the most valuable asset, but its security and ethical management are critical.

I built this project to answer a fundamental data safety question: **Is simply removing names and IDs enough to protect patient privacy in a Big Data environment?** 

By leveraging **Google Colab** and advanced Python manipulation, I simulated a real-world security challenge, analyzing over **1.1 million clinical records** to mathematically test the limits of data anonymization and $k$-anonymity principles.

---

## Key Analytical Metrics Achieved
* **Massive Scale:** Engineered an automated workflow in Google Colab to fetch and process a relational healthcare ecosystem containing **1,143,900 rows of clinical diagnoses**.
* **Methodological Iteration:** Optimized the re-identification algorithm through 3 evolutionary phases, boosting the attack success rate from a misleading **0.20%** up to a definitive **85.05% theoretical limit**.
* **Impact Visualized:** Proven that a multi-dimensional linkage attack can compromise and expose the medical secrecy of **972,933 simulated patients** without exploiting network infrastructure, relying purely on demographic data correlation.

---

## The Data Analyst Stack & Techniques Used
* **Cloud Infrastructure:** Google Colab (leveraging cloud storage and virtualized processing).
* **Data Wrangling & Manipulation:** Python 3, Pandas (Complex merges, relational mapping, handling 1-to-Many longitudinal records).
* **Data Cleaning & Imputation:** Advanced handling of missing values (`NaN`) using strategic imputation to eliminate survival bias in demographic minority segments.
* **Core Concepts Applied:** Data Re-identification, Quasi-Identifiers (QIs) isolation, Linkage Attacks, Entropy Limits, and $k$-Anonymity evaluation.

---

## Step-by-Step Analytical Workflow

### 1. Cloud Data Ingestion (Kaggle API integration)
To handle a dataset of this scale efficiently without breaking local RAM, I configured a direct pipeline between Kaggle's cloud storage and Google Colab using Kaggle's direct API Token access.

### 2. Handling the 1-to-Many Relational Trap
During exploratory data analysis (EDA), the consolidated database exploded to **1,143,900 rows**. I discovered that clinical data is longitudinal: *one unique patient maps to multiple recorded medical conditions over their lifetime*.

### 3. Data Imputation over Data Dropping
A standard data dropping method (`dropna()`) wiped out nearly 130,000 incomplete records (mainly pediatric patients lacking marital status data), biasing the dataset. I resolved this professionally by implementing data imputation, replacing null parameters with an `'Unknown'` category flag. This kept the dataset statistically complete and exposed a wider surface of unique demographic profiles.

### 4. Maximum Dimensionality Asymmetric Linkage Attack
I structured an asymmetric algorithm that isolated individuals who were statistically unique in a simulated public registry based on an expansive set of **Quasi-Identifiers (QIs)**:
`['BIRTHDATE', 'GENDER', 'ZIP', 'RACE', 'MARITAL', 'CITY', 'ETHNICITY']`

By matching these unique identifiers back to the hospital database without erasing duplicates, the algorithm extracted the entire historical diagnosis history for each isolated target.

---

## How to Inspect My Work in Google Colab

Since Big Data management requires cloud reproducibility, you can run my entire data pipeline directly:

1. Clone this repository to your machine or download the notebook file from the `notebooks/` folder.
2. Upload the `linkage_attack_analysis.ipynb` file directly into your **Google Colab** environment.
3. Obtain your personal API Token from your Kaggle account settings interface.
4. Paste your token into the initial configuration cell to trigger the automated direct download and decompression of the **Synthea COVID-19 100k Dataset**.
5. Run all cells to replicate the analytical metrics and witness the 85.05% re-identification threshold.

> **Ethical Research Disclaimer:** This analytical study was conducted strictly using **100% high-fidelity synthetic data** generated via the open-source Synthea medical simulator framework. No real patient records, personal identifiable information (PII), or institutional healthcare infrastructure were compromised, accessed, or altered during this research.
