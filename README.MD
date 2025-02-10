# **Advanced Data Analysis and GitHub Workflow** <br> **Name:** Daryl Bubune Atito Narh <br> **Roll No.:** 10211100222


## **Task 1: Data Quality Assessment**

### **Are there any duplicate rows? If yes, why might duplicates exist in this dataset?**
There are no duplicate rows in the dataset. However, if there were, it would be as a reult of:
1. Data entry errors.
2. Data merging issues.
3. Repeated transactions or logs.

### **Are there inconsistencies in categorical values (e.g., spelling variations, case sensitivity)?**
There are no incosistencies in the categorical values.

### **What should we do if a column has too many missing values?**
1. If a column has too many missing values (e.g., > 50-60%), consider dropping it.
2. If the information within is valuable, we can replace by filling it (mean/median for numerical, mode for categorical, ffil or bfill).

### **Are there outliers in numerical columns? If so, should we remove or adjust them?**
There are no numerical outliers. But if they existed, we would do the following:
1. Remove them, if the outliers are due to errors.
2. If they are extreme but valid, use transformations to normalize them.
3. If they are critical, keep them but analyze their impact on the model.

## **Task 2: Dataset Documentation & Collaboration**

### **If you were a new data scientist joining this project, what would you need to understand this dataset?**
1. A document explaining each column's meaning, data types, and expected values.
2. Why was this dataset collected? What is the Context & Goals of the dataset?
3. How was the data collected? Were there transformations applied?
4. Insights on missing values, duplicates, inconsistencies, and potential biases.
5. Version History

### **How do you write effective column descriptions?**
* Column Name – The exact name used in the dataset. 
* Definition – What the column represents.
* Data Type – Integer, float, string, boolean, datetime, etc.
* Unit of Measurement (if applicable) – E.g., "kilograms," "USD," "percentage."
* Possible Values – Categories for categorical data or valid ranges for numerical data.
* Example Values – A real or synthetic example to illustrate.

### **What’s the best way to track changes in a dataset over time?**
* Version Control with Git
* Add created_at and updated_at columns to track record modifications.
* Data Logging
* Use a DVC (Data Version Control) similar to Git but optimized for large datasets.
* Use frameworks like Delta Lake for versioned data tracking, especially for big data.
* Maintain a structured changelog.md file documenting updates, fixes, and schema changes.