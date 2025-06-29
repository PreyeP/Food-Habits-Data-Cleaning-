# Food-Habits-Data-Cleaning-
##Table of Contents
- [Project Overview](#project-overview)
- [Project Goal](#project-goal)
- [Data Source](#data-source)
- [Tools & Technologies](#tools--technologies)
- [Data Cleaning & Preparation](#data-cleaning--preparation)
- [Conclusion](#conclusion)
## Project Overview
This project focuses on cleaning and preparing the "Food Coded" dataset to enable robust analysis of food habits and their correlation with various lifestyle factors. The raw data has undergone rigorous cleaning, including handling missing values, standardizing formats, and removing inconsistencies. Furthermore, the columns have been thoughtfully renamed and logically rearranged to enhance usability and interpretability, making it easier to explore relationships between food choices, lifestyle factors, and various demographic characteristics. This dataset is now optimized for insightful analysis into dietary patterns and their correlations.

![After cleaning the dataset](https://github.com/user-attachments/assets/e425cd76-966b-4ec4-a97c-9967608ae452)

## Project Goal
The primary objective of this data cleaning initiative was to enhance the accuracy of analysis and improve the readability of the dataset for a diverse audience by transforming the messy raw dataset into a clean, well-structured dataset suitable for statistical analysis. This dataset specifically explores the eating habits and lifestyle of college students.
## Data Source
This repository hosts the `food_coded.csv` dataset, originally sourced from kaggle.com [download here](https://www.kaggle.com/datasets/borapajo/food-choices?select=food_coded.csv) as part of a comprehensive data cleaning project.
## Tools & Technologies
-Microsoft Excel [download here](https:/microsoft.com)
## Data Cleaning & Preparation
This section outlines the systematic approach used to transform the raw `food_coded.csv` dataset into a clean, structured, and analysis-ready format.
### Initial State of Data
The raw dataset presented several challenges that necessitated cleaning to ensure data veracity and usability. Key issues identified included:
- Lack of a unique student identifier.
- Inconsistent formatting in column headers.
- Presence of missing values (represented as "nan" or blanks) in various columns.
- Incorrect data types (e.g., numerical representations for gender).
-Duplicated columns.
-Inconsistent text formatting and extraneous spaces in descriptive fields.

### Data Cleaning Methodology

A systematic approach was employed to address the identified data quality issues. The steps undertaken are detailed below:

#### Dataset Preservation
The entire raw dataset was copied to a new worksheet to ensure the preservation of the original data and to facilitate tracking of all modifications.

#### Unique Student Identification
-Problem: The dataset lacked a unique identifier for individual students, hindering data analysis and readability.
-Solution: A new column was inserted at the beginning of the dataset (Column A) and populated with unique student codes, which were then dragged down to fill all rows.

#### Standardization of Column Headers
-Problem: Column headers were not in a standardized text format, impacting readability and potential automation.
-Solution:
    -A new temporary row was inserted above the existing headers.
    -The formula `=CLEAN(TRIM(PROPER(A2))) ` was applied to the new row (starting from A1, referencing A2 for the original header), and dragged across to clean and standardize all headers. This formula ensured that headers were properly capitalized, leading and trailing spaces were removed, and non-printable characters were eliminated.
    -The cleaned headers were then copied and "pasted special" as "Values" back into the original header row, overwriting the uncleaned data.
    -The temporary row was subsequently deleted.
    -Additionally, almost all the column headers were further renamed to be more intuitive and understandable for a broader audience.

#### Handling Missing Numerical Data
-GPA: Missing or zero values in the `GPA` column were imputed with the average GPA of the column. The `GPA` values were then consistently rounded to one decimal place.
-Student Weight: Blank cells in the student `weight` column were filled with the average weight of the column.
-Other Numerical Columns: Any other numerical columns containing blank cells were similarly filled using the average of their respective columns.

#### Addressing Missing Text Data
-General Text Columns: Blank cells in text columns were uniformly filled with "None".
-Inconsistent Text Formats and Spaces: A "Find & Replace" function (CTRL+H) was utilized to replace double spaces " " with single spaces " " across all text columns.

#### Data Type Correction
 -The ‘Gender’ column, which contained numerical representations (1 and 2), was formatted as text, with '1' representing "Male" and '2' representing "Female". This was achieved by using the IF function `=IF(B2=2,“Female”,“Male”)`

#### Text Field Standardization (Description Columns)
-Problem: Description columns exhibited inconsistent text formats and extraneous spaces.
-Solution: 
- A new temporary column was inserted.
-The formula `=UPPER(LEFT(AL2,1))&RIGHT(AL2,LEN(AL2)-1)` was applied to format the text into proper case (first letter capitalized, rest lowercase), and dragged down the column.
  -The cleaned values were then copied and "pasted special" as "Values" back into the original description column.
   -The temporary column was deleted.

#### Duplicate Column Removal
Some identified duplicate columns were removed from the dataset to ensure data uniqueness and avoid redundancy.

#### Spelling Error Correction
Spelling errors for the text columns were checked using the "Review Tab" > "Spelling" function in Excel.

#### Logical Column Arrangement
Finally, all columns were logically reorganized to enhance readability and facilitate more intuitive data exploration and analysis. The new arrangement groups related information as follows:
1. Student Core Information & Demographics: `Student_Gender`, `Student_Grade_Level`, `Grade_Point_Average`, `Student_Weight`, `Self_Perception_Of_Weight`, `Marital_Status`, `On_Off_Campus_Living`, `Employment_Status`.
2. Family Background: `Father_Education_Level`, `Father_Profession`, `Mother_Education_Level`, `Mother_Profession`, `Household_Income`.
3. Daily Eating Habits & Diet Patterns: `Breakfast_Frequency`, `Eating_Out_Frequency`, `Meal_Payment_Method`, `Cooking_Frequency`, `Parents_Cooking_Frequency`, `Meals_Cooked_For_Friends`, `Current_Diet_Coded`, `Description_Of_Current_Diet`, `Ideal_Diet_Coded`, `Description_Of_Ideal_Diet`, `Healthy_Eating_Feeling`, `Description_Of_Healthy_Meal`, `Nutritional_Check_Frequency`, `Vitamin_Supplement_Use`.
4. Changes in Eating Habits: `Changes_In_Eating_Habits`, `Changes_In_Eating_Habits_Coded`.
5. Food Preferences & Specific Consumption: `Favorite_Food_Type`, `Favorite_Childhood_Food`, `Favorite_Cuisine`, `Favorite_Cuisine_Coded`, `Cuisine_Preferences`, `Ethnic_Food_Preference`, `Indian_Food_Preference`, `Italian_Food_Preference`, `Greek_Food_Preference`, `Persian_Food_Preference`, `Thai_Food_Preference`, `Fries_Consumption`, `Soup_Consumption`, `Coffee_Consumption`, `Drink_Consumption`, `Fruits_Per_Day_Servings`, `Vegetables_Per_Day_Servings`.
6. Calorie Information: `Estimated_Daily_Calorie_Intake`, `Calories_From_Chicken_Dinner`, `Calories_From_Scone_Dinner`, `Calories_From_Tortilla_Dinner`, `Calories_From_Turkey_Dinner`, `Calories_From_Waffle_Dinner`.
7. Comfort Food Details: `Comfort_Foods_Eaten`, `Reasons_For_Comfort_Food`, `Reasons_For_Comfort_Food_Coded`.
8. Physical Activity & Well-being: `Exercise_Frequency`, `Sports_Participation`, `Type_Of_Sports_Played`, `Life_Rewarding_Feeling`.

## Conclusion
Through these comprehensive cleaning steps, the college student food dataset has been transformed into a well-structured, accurate, and easily interpretable resource, ready for robust analysis to derive meaningful insights into student eating habits and lifestyles.

