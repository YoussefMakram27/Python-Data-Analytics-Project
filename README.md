# Python-Data-Analytics-Project-Charts

<img width="541" height="402" alt="image-1" src="https://github.com/user-attachments/assets/49c589f7-cae8-4ac2-8776-082d89ff41a1" />

<img width="541" height="402" alt="image-1" src="https://github.com/user-attachments/assets/dcee9505-312b-46e0-b423-7b4d514369a7" />

<img width="541" height="402" alt="image-2" src="https://github.com/user-attachments/assets/5b19f388-72e4-40dd-9552-6188b430ab29" />

<img width="550" height="402" alt="image-3" src="https://github.com/user-attachments/assets/27d21f18-a6a1-4486-aa26-d00729ddb01b" />

<img width="770" height="479" alt="image-4" src="https://github.com/user-attachments/assets/f9d74914-c7bc-40cc-b319-54da58fd4bcd" />

<img width="562" height="378" alt="image-5" src="https://github.com/user-attachments/assets/ab363245-ed4b-4e76-b48e-19554354fa07" />

<img width="1384" height="583" alt="image-6" src="https://github.com/user-attachments/assets/680b064a-b58c-4328-92e8-6f7445bddc54" />

# Users Data Pipeline & Analysis

This project demonstrates a **simple end-to-end data pipeline** built using Python.  
It covers **data ingestion from an API, data exploration, data transformation, and data analysis with visualizations**.

The project was completed as part of the **Data Engineering Track at ITI (Information Technology Institute)**.

---

# Project Overview

The goal of this project is to practice the core steps of a small data engineering workflow:

1. **Data Ingestion** – Collect data from an external API  
2. **Data Exploration** – Understand dataset structure and quality  
3. **Data Transformation** – Clean and normalize nested JSON data  
4. **Data Analysis** – Generate insights using statistical analysis and visualizations  

Dataset Source:  
https://dummyjson.com/users

---

# Project Structure

```
.
├── read.py        # Collect data from API and save to CSV
├── Data-Exploration.py            # Exploratory data analysis
├── Data-Transformation.py         # Data cleaning and transformation
├── Data-Analysis.py               # Data analysis and visualization
├── users.csv                 # Raw collected data
├── cleaned_users.csv         # Processed dataset
└── README.md
```

---

# Step 1 – Data Ingestion

User data is collected from the API using **Python Requests**.

Features:

- Pagination handling (`limit` and `skip`)
- Iterative API requests until all records are collected
- Convert API response to **Pandas DataFrame**
- Store dataset locally as CSV

Key libraries:

```
requests
pandas
```

Output:

```
users.csv
```

---

# Step 2 – Data Exploration

Initial exploration was performed to understand the dataset.

Checks included:

- Dataset shape
- Column names
- Data types
- Missing values
- Duplicate rows
- Summary statistics
- Distribution of categorical variables

Example explored columns:

- gender
- bloodGroup
- role
- eyeColor

Tools used:

```
pandas
```

---

# Step 3 – Data Transformation

Several fields in the dataset contained **nested JSON objects stored as strings**.

Custom functions were implemented to clean and normalize the data.

## Address Parsing

Extract **city** from the address object.

## Crypto Parsing

Extract **coin name** from cryptocurrency data.

## Company Parsing

Extract:

- company name  
- company city  

## Flattening Nested Columns

The following columns were flattened using `pandas.json_normalize`:

- bank
- hair

Example resulting fields:

```
bank.cardExpire
bank.cardNumber
bank.cardType
hair_color
hair_type
```

## User Agent Parsing

Extracted the **operating system** from the `userAgent` string.

Example:

```
Mozilla/5.0 (Windows NT 10.0; Win64; x64)
```

becomes

```
Windows NT 10.0
```

Output dataset:

```
cleaned_users.csv
```

---

# Step 4 – Data Analysis & Visualization

Using **Pandas, Matplotlib, and Seaborn**, several questions were explored.

## 1. What is the average age of users?

- Calculated overall mean age
- Visualized age distribution with histogram

## 2. Average age by gender

- Grouped by gender
- Visualized using bar plot

## 3. Number of users per gender

- Counted gender distribution
- Displayed with count plot

## 4. Top 10 cities with most users

- Aggregated city counts
- Visualized using horizontal bar chart

## 5. Average height and weight

- Calculated mean values
- Displayed distribution using box plots

## Relationship Analysis

Scatter plots were created to analyze relationships between:

- Age vs Height
- Age vs Weight

Regression lines were added to observe trends.

Libraries used:

```
pandas
matplotlib
seaborn
numpy
```

---

# Technologies Used

- Python
- Pandas
- NumPy
- Requests
- Matplotlib
- Seaborn

---

# Skills Practiced

This project helped practice important **data engineering and data processing skills**:

- API data ingestion
- Handling paginated APIs
- JSON parsing
- Data cleaning and normalization
- Working with nested data structures
- Data exploration
- Data visualization
- Building a simple ETL-style workflow

---

# Future Improvements

Possible extensions to this project:

- Store data in **PostgreSQL or DuckDB**
- Build an **Airflow pipeline**
- Process data with **PySpark**
- Store data in **Parquet format**
- Add **data validation checks**
- Containerize pipeline using **Docker**

---

# Author

**Youssef M.Makram M.Osman**

Data Engineering Trainee – ITI

GitHub: *https://github.com/YoussefMakram27*  
LinkedIn: *www.linkedin.com/in/youssef-m-makram*
