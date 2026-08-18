# SaaS Customer Data Management & Analysis

## 📌 Project Overview

This project is a Python-based **SaaS Customer Data Management and Analysis** project developed as part of a Python Module End Assessment.

The project demonstrates practical Python and beginner-level Data Science concepts, including:

* Working with dictionaries and lists
* Using `for` loops and conditional statements
* Adding customer records dynamically
* Object-Oriented Programming (OOP)
* Data validation and cleaning
* Handling missing and invalid values
* Standardizing date formats
* Removing duplicate records
* Calculating summary statistics
* Identifying low-usage customers
* Finding unique SaaS plans
* Saving processed customer information to files

The original dataset contains customer information such as customer ID, name, signup date, subscription plan, monthly fee, and usage hours.

---

## 🎯 Project Objectives

The main objectives of this project are to:

1. Display SaaS customer records in a readable format.
2. Add new customer records dynamically.
3. Create a reusable `SaaSCustomer` class.
4. Validate and clean customer data.
5. Standardize different date formats.
6. Handle missing values.
7. Remove duplicate customer records.
8. Calculate basic customer statistics.
9. Identify customers with low product usage.
10. Extract unique subscription plans.
11. Save processed customer information into output files.

---

## 🗂️ Dataset

The project works with the following customer attributes:

| Column        | Description                                   |
| ------------- | --------------------------------------------- |
| `customer_id` | Unique customer identifier                    |
| `name`        | Customer name                                 |
| `signup_date` | Customer registration date                    |
| `plan`        | SaaS subscription plan                        |
| `monthly_fee` | Monthly subscription fee                      |
| `usage_hours` | Number of hours the customer uses the service |

The initial dataset contains 7 customer records and intentionally includes data-quality issues such as missing names, inconsistent dates, invalid monthly fees, missing usage values, and an empty plan.

---

## 🧹 Data Cleaning

Several data-cleaning operations are implemented in the project.

### 1. Date Standardization

Different date formats are converted into a common:

```text
YYYY-MM-DD
```

The project handles formats such as:

```text
2023-01-10
2023/02/15
03-01-2023
15-04-2023
20230520
```

The cleaned dataset standardizes these dates, for example `2023/02/15` becomes `2023-02-15`.

### 2. Missing Names

Missing customer names are replaced with:

```text
Unknown Customer
```

### 3. Missing Usage Hours

Missing, empty, `NULL`, or `None` usage values are converted to:

```text
0
```

This logic is implemented in the missing-value handling function.

### 4. Invalid Monthly Fees

Invalid monthly fee values such as:

```text
forty-nine
```

are identified as invalid during the cleaning process. The cleaned CSV represents the invalid value as an empty field.

### 5. Duplicate Records

The project includes logic to identify repeated customer names and retain unique records.

---

## 🐍 Object-Oriented Programming

A `SaaSCustomer` class is created to represent individual SaaS customers.

The class contains attributes including:

```python
customer_id
name
signup_date
plan
monthly_fee
usage_hours
```

It also contains methods for:

* Validating customer data
* Displaying customer information

The `validate_data()` method converts monthly fees to `float`, usage hours to `int`, handles missing names, and standardizes plan names.

---

## 📊 Data Analysis

The project calculates basic SaaS customer statistics including:

* Total number of customers
* Average monthly fee
* Total usage hours
* Number of customers per subscription plan

The notebook calculates the average fee by converting valid fee values to floating-point numbers and handles invalid values using exception handling.

---

## 📉 Low-Usage Customer Analysis

A function called:

```python
find_low_usage_customers()
```

identifies customers whose usage is below:

```text
50 hours
```

The function displays:

```text
ID
Name
Plan
Usage Hours
```

for each low-usage customer.

This type of analysis can help a SaaS business identify customers who may need:

* Product education
* Customer support
* Engagement campaigns
* Onboarding assistance
* Retention strategies

---

## 📦 Subscription Plan Analysis

The project extracts unique subscription plans using Python's `set()` data structure.

The empty plan value is replaced with:

```text
Unknown
```

and the resulting plans are sorted alphabetically.

The accompanying plan-summary file reports:

| Plan    | Customers |
| ------- | --------: |
| Basic   |         2 |
| Pro     |         4 |
| Premium |         1 |

---

## 💾 Output Files

The project produces/uses cleaned customer data in CSV format.

### `saas_customers_cleaned.csv`

The cleaned dataset contains:

```text
customer_id,name,signup_date,plan,monthly_fee,usage_hours
```

Example cleaned records include standardized dates, `"Unknown Customer"` for missing names, `"Unknown"` for a missing plan, and `0` for missing usage hours.

### `Customer_plan_Data_summary.txt`

The notebook also creates a text summary containing the number of customers in each plan.

---

## 🛠️ Technologies Used

* **Python 3**
* Python Lists
* Python Dictionaries
* `for` loops
* Conditional Statements
* Functions
* Exception Handling (`try`, `except`)
* Object-Oriented Programming
* `datetime`
* `pandas`
* CSV files
* Text files

---

## 📁 Project Structure

```text
SaaS-Customer-Data-Analysis/
│
├── Python_Module_End_Assessment_1.ipynb
├── saas_customers_cleaned.csv
├── Customer_plan_Data_summary.txt
└── README.md
```

---

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone <your-github-repository-url>
```

### 2. Open the Jupyter Notebook

Open:

```text
Python_Module_End_Assessment_1.ipynb
```

using Jupyter Notebook, JupyterLab, or Google Colab.

### 3. Run the cells

Execute the notebook cells sequentially to:

* Display the dataset
* Add customer records
* Validate customer data
* Clean the dataset
* Analyze customer usage
* Identify unique plans
* Generate output files

---

## 📈 Key Data Science Concepts Demonstrated

This project helped demonstrate the following foundational concepts:

### Data Collection

Working with structured customer information stored in Python dictionaries.

### Data Cleaning

Handling missing, invalid, inconsistent, and duplicate data.

### Data Transformation

Converting dates, fees, and usage values into usable formats.

### Exploratory Data Analysis

Calculating customer counts, average fees, usage totals, and plan distributions.

### Feature Validation

Checking and standardizing customer attributes.

### Business Analysis

Identifying low-usage customers and understanding subscription-plan distribution.

---

## 💡 Business Insights

The project demonstrates how raw SaaS customer data can be transformed into useful business information.

For example, identifying customers with usage below 50 hours can help a SaaS company focus its customer-success efforts on potentially less-engaged users.

Subscription-plan analysis can also help understand how customers are distributed across different plans.

---

## 🎓 Learning Outcome

Through this project, I practiced moving from **raw data → data cleaning → validation → analysis → output generation** using Python.

The project strengthened my understanding of:

```text
Python Fundamentals
        ↓
Functions
        ↓
OOP
        ↓
Exception Handling
        ↓
Data Cleaning
        ↓
Data Analysis
        ↓
Business Insights
```

This project represents a foundation for progressing toward more advanced **Data Science, Data Analysis, SQL, Pandas, Statistics, Machine Learning, and Visualization** projects.

---

## 👤 Author

**Jaxson**

Aspiring Data Scientist

---

## ⭐ Future Improvements

Possible future enhancements include:

* Use Pandas for the complete data-cleaning pipeline
* Add data visualizations using Matplotlib and Seaborn
* Perform deeper customer segmentation
* Calculate customer lifetime value
* Analyze revenue by subscription plan
* Build a customer churn prediction model
* Add automated data-quality checks
* Create an interactive dashboard
* Store customer data in a SQL database

---

## 📜 Project Status

**Completed — Python Module End Assessment 1**

This project is intended as a learning and portfolio project demonstrating foundational Python and Data Science skills.
