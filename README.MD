# **Advanced Data Analysis and GitHub Workflow**

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