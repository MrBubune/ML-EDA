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


## **Task 3: Relationship Analysis**

### Does gender influence dating app preferences?
From the Chi-Square test, it has a weak relation (p is 0.1833, which is >0.05, indicating a weak relationship).

### Are people using multiple dating apps simultaneously?
Yes, multiple app engagement is common

### Which age group is most active on dating apps?
The most active age group is 18 year olds, 23 year olds and 24 year olds.

### Do people in urban vs. rural areas show different usage patterns?
Urban users (Mumbai and Dehli specifically) use dating apps far more than rural users.


## **Task 4: Detecting Patterns & Bias in Data**

### **Is there gender bias in dating app usage?**
Gender Distribution is 35.2% females, 34.2% males and 30.6% non-binary, indicating a very weak bias.
### **Are certain demographics overrepresented in the dataset?**
We would have to compare the dataset’s age, education, and location distribution with real-world Gen-Z demographics in India.

### **Is there a missing group of users that should have been included?**
We would have to identify underrepresented groups (e.g., rural users, non-binary users, certain age groups).

### **Can we trust this dataset for making general claims about Gen-Z dating in India?**
Compare dataset proportions to India's Gen-Z demographics (external validation would be needed)


## **Task 5: Temporal & Regional Trends**

### **Are younger or older Gen-Z users more active on dating apps?**
Younger users have higher median usage frequency, they are more active.

### **Does dating app preference change over time?**
If some apps are gaining popularity over time, it indicates shifting user preferences. If they are declining, they may be losing relevance.

### **Do metro city users behave differently from users in smaller towns?**
Smaller-town users prefer all the apps, highlighting their regional app preferences


## **Task 6: Feature Engineering for Future Modeling**

### **How can we convert categorical variables into numbers for ML models?**
1. One-Hot Encoding (OHE) → For unordered categories (e.g., Gender, Primary_App)
2. Label Encoding → For ordered categories (e.g., Satisfaction Levels: Low, Medium, High)
3. Ordinal Encoding → If there's a meaningful order (e.g., Subscription Plan: Free < Silver < Gold)

### **Should we normalize numerical data? Why or why not?**
*When to Normalize?*<br>
* If numerical features have different scales, normalization improves model performance (especially for distance-based models like KNN & SVM).
* If values range widely (e.g., Age: 18-25 vs. App Usage Hours: 0-1000), it prevents some features from dominating others.

*When to Skip Normalization?*<br>
* If using tree-based models (Random Forest, Decision Trees, XGBoost)
* If all numerical values are already in the same range.

### **What new features could we create to enhance predictive modeling?**
|Feature Name	    |Description                                                                    |
|-------------------|-------------------------------------------------------------------------------|
|Age_Group	        |Categorize users into age brackets (e.g., 18-21, 22-25)                        |
|Active_Hours	    |Convert usage frequency into a numerical scale (e.g., Daily = 7, Weekly = 1)   |
|Engagement_Score	|Based on time spent per session × sessions per week                            |
|Urban_vs_Rural	    |Binary feature: 1 = Metro, 0 = Small town                                      |
|Loyalty_Score	    |How long a user has been on a specific app (if data is available)              |
|Diversity_of_Apps	|Number of dating apps used (Primary + Secondary Apps)                          |
|High_Paying_User	|Binary: 1 if using a paid subscription, 0 otherwise                            |


## **Task 7: Collaborative Review & Documentation**

### **What Were the Most Surprising Insights from This Dataset?**  
- Many users engage with multiple dating apps, suggesting a lack of loyalty to a single platform.  
- Urban users tend to have higher daily usage time compared to rural users.  
- Older Gen-Z users (22–25) are more likely to use serious relationship apps, while younger users (18–21) prefer casual connections.  

### **What Would You Do Differently If Given More Time?**   
- Create more behavioral features (e.g., time spent per session, match success rate).  
- Use NLP techniques to analyze "Reason for Using" responses for sentiment.   
- Better handling of missing values using imputation.  
- Identify and remove potential duplicates.    
- Apply clustering techniques to segment users.  
- Conduct time-series analysis on app engagement trends.  


### **How Can We Improve Dataset Documentation for Others?**  
- Clearly define each column’s meaning, data type, and possible values.  
- Version Control  
- Document transformations applied (e.g., encoding, normalization) so others can understand the preprocessing.  
- Use correlation heatmaps, histograms, and boxplots in the README file for a quick dataset overview.  
