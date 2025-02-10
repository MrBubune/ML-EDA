# GenZ Dating App Dataset

## Overview
This dataset contains information about Gen Z users' dating app preferences, behaviors, and satisfaction levels. It includes demographic details, app usage patterns, and desired features.

## Column Descriptions

| Column Name               | Data Type  | Description |
|---------------------------|-----------|-------------|
| `User_ID`                | Integer   | Unique identifier for each user. |
| `Age`                    | Integer   | User's age in years (e.g., 18, 24, 30). |
| `Gender`                 | String    | Self-reported gender (e.g., "male", "female", "non-binary"). |
| `Location`               | String    | User's city or region (e.g., "Delhi", "Bangalore"). |
| `Education`              | String    | Highest level of education attained (e.g., "Undergraduate", "Graduate"). |
| `Occupation`             | String    | User's current occupation (e.g., "Freelancer", "Intern", "Full-time job"). |
| `Primary_App`            | String    | The dating app the user primarily uses (e.g., "Tinder", "Hinge"). |
| `Secondary_Apps`         | String    | Other dating apps the user occasionally uses (e.g., "OkCupid", "Hinge"). |
| `Usage_Frequency`        | String    | How often the user engages with dating apps (e.g., "Daily", "Weekly", "Monthly"). |
| `Daily_Usage_Time`       | String    | Estimated time spent on dating apps per day (e.g., "30 minutes", "2 hours"). |
| `Reason_for_Using`       | String    | Primary reason for using dating apps (e.g., "Finding a partner", "Casual fun"). |
| `Satisfaction`           | Integer   | User's satisfaction rating (scale: 1 = Very Dissatisfied, 5 = Very Satisfied). |
| `Challenges`             | String    | Issues faced while using dating apps (e.g., "Safety concerns", "Time-wasting"). |
| `Desired_Features`       | String    | Features users wish to see in dating apps (e.g., "Video calls", "AI recommendations"). |
| `Preferred_Communication`| String    | Preferred mode of communication with matches (e.g., "Text", "Voice notes"). |
| `Partner_Priorities`     | String    | Factors users prioritize when choosing a partner (e.g., "Values > Personality > Appearance"). |

## Data Cleaning Steps Taken

1. **Handled Missing Values:**
   - Dropped columns with more than 60% missing values.
   - Filled missing numerical values with the median.
   - Filled missing categorical values with the most common (mode).

2. **Removed Duplicates:**
   - Identified and dropped duplicate rows to ensure data integrity.

3. **Standardized Categorical Values:**
   - Converted text to lowercase and stripped whitespace to maintain consistency.

4. **Handled Outliers:**
   - Used the Interquartile Range (IQR) method to detect and remove extreme values from numerical columns.

5. **Saved Cleaned Dataset:**
   - Exported the processed dataset as `cleaned_GenZ_DatingApp_Data_v1.csv` for further analysis.

## Notes
- **Categorical variables** like `Gender`, `Primary_App`, and `Challenges` may have variations and should be standardized for analysis.
- **Satisfaction** is measured on a **1-5 scale**, with 5 being the highest rating.
- **Usage Frequency** and **Daily Usage Time** provide insights into user engagement levels.

