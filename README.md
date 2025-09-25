# Big Data Analytics with PySpark - Task Notebook

This repository contains a comprehensive PySpark notebook that demonstrates various big data processing techniques using Apache Spark. The notebook covers fundamental operations with RDDs (Resilient Distributed Datasets) and DataFrames, including data manipulation, analysis, and text processing.

## 📋 Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Notebook Structure](#notebook-structure)
- [Features](#features)
- [Usage](#usage)
- [Examples](#examples)
- [Results](#results)

## 🔍 Overview

This notebook serves as a practical guide for learning PySpark fundamentals through hands-on exercises. It covers:

- **RDD Operations**: Creating and manipulating RDDs with various transformations and actions
- **DataFrame Operations**: Working with structured data using Spark DataFrames
- **Text Processing**: Analyzing text data with word frequency analysis and stopword removal
- **Statistical Analysis**: Computing aggregations, filtering, and grouping operations
- **Data Cleaning**: Handling null values and data preprocessing

## 🛠 Prerequisites

Before running this notebook, ensure you have:

- **Python 3.7+**
- **Apache Spark 3.0+**
- **PySpark**
- **NumPy**
- **Jupyter Notebook or JupyterLab**

## 📦 Installation

### 1. Install Apache Spark
```bash
# Download Spark from https://spark.apache.org/downloads.html
# Extract and set environment variables
export SPARK_HOME=/path/to/spark
export PATH=$PATH:$SPARK_HOME/bin
```

### 2. Install Python Dependencies
```bash
pip install pyspark numpy jupyter
```

### 3. Start Jupyter Notebook
```bash
jupyter notebook
```

## 📚 Notebook Structure

The notebook is organized into several main sections:

### 1. **Setup and Configuration**
- Import necessary libraries
- Initialize SparkSession
- Create SparkContext

### 2. **RDD Operations**
- **Number Analysis**: Create RDD from numbers 1-50 and perform statistical operations
- **People Data Analysis**: Analyze person information (name, age) with various operations
- **Text Processing**: Analyze Russia-related text with word frequency and stopword removal

### 3. **DataFrame Operations**
- **Employee Data**: Work with structured employee data including filtering and aggregation
- **Data Cleaning**: Handle null values in CSV data

## ✨ Features

### RDD Operations
- ✅ Create RDD from list of numbers using NumPy
- ✅ Compute statistical measures (sum, average, max, min, count)
- ✅ Count even vs odd numbers
- ✅ Find oldest person in dataset
- ✅ Compute average age
- ✅ Group names by age

### Text Processing
- ✅ Load text data from file into RDD
- ✅ Count total lines and specific word occurrences
- ✅ Find most frequent words
- ✅ Tokenize words and remove stopwords
- ✅ Calculate word frequency

### DataFrame Operations
- ✅ Create DataFrames with custom schema
- ✅ Select specific columns
- ✅ Apply filters and aggregations
- ✅ Handle null values with data imputation
- ✅ Group by operations with average calculations

## 🚀 Usage

1. **Clone or download the notebook**
2. **Ensure all dependencies are installed**
3. **Start Jupyter Notebook**
4. **Open `Task.ipynb`**
5. **Run cells sequentially or execute specific sections**

### Required Files
Make sure you have these files in your `/data/` directory:
- `russia.txt` - Text file containing information about Russia
- `NullData.csv` - CSV file with employee data containing null values

## 📊 Examples

### Statistical Analysis Example
```python
# Create RDD from numbers 1-50
numbers_rdd = sc.parallelize(list(range(1, 50)))

# Calculate sum
total_sum = numbers_rdd.sum()  # Result: 1225

# Calculate average
average = numbers_rdd.mean()   # Result: 25.0
```

### Text Analysis Example
```python
# Load text file
rdd_russia = sc.textFile("/data/russia.txt")

# Count lines containing "Russia"
russia_count = rdd_russia.filter(lambda line: "Russia" in line).count()
```

### DataFrame Operations Example
```python
# Create DataFrame
df = spark.createDataFrame(data, schema)

# Filter employees older than 28
older_employees = df.filter(df.age > 28)
```

## 📈 Results

### Key Statistics
- **Number Range Analysis**: Numbers 1-50
  - Sum: 1,225
  - Average: 25.0
  - Even Numbers: 24
  - Odd Numbers: 24

### Text Analysis Results
- **Total Lines**: 8
- **Lines containing "Russia"**: 6
- **Top 5 Frequent Words**: 'is', 'the', 'Russia', 'in', 'world'

### Employee Data Analysis
- **Average Salary**: 6,000
- **Employees older than 28**: 2 (Mariam, Omar)
- **Distinct Names**: 4 (Ali, Mariam, Omar, Sara)

## 🔧 Data Files

The notebook expects the following data files in a `/data/` directory:

### russia.txt
Contains 8 lines of text about Russia, covering topics like:
- Geographic information
- Capital city
- Language and culture
- Transportation
- History and traditions

### NullData.csv
Contains employee data with the following structure:
- Id: Employee identifier
- Name: Employee name (some null values)
- Sales: Sales amount (some null values)

## 📝 Notes

- The notebook demonstrates both RDD and DataFrame APIs
- Some cells may appear empty but contain executed code with output
- Results are shown in the output cells for reference
- The notebook covers fundamental Spark operations suitable for beginners
- All examples use small datasets for demonstration purposes

## 🤝 Contributing

Feel free to contribute to this notebook by:
- Adding more examples
- Improving documentation
- Fixing any issues
- Adding new features

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

**Happy Learning with PySpark! 🚀**
