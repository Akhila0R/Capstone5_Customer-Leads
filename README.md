# Capstone5_Customer-Leads
# Table of Contents
- [Problem Statement](#problem-statement)
- [Information About Dataset and Cleaning](#information-about-dataset-and-cleaning)
- [Data Cleaning Steps](#data-cleaning-steps)
- [Insights from EDA](#insights-from-eda)
- [License](#license)
# Problem Statement
The Edu-Tech company is seeking to improve its customer acquisition process, optimize marketing strategies, and enhance lead conversion rates by leveraging its customer data. The objective is to analyze this data to gain insights into customer behaviors, preferences, and conversion patterns. These insights will be used to prioritize leads with the highest likelihood of conversion, refine marketing and sales strategies, and optimize resource allocation.
Key questions to address include:

1. Which leads are most likely to convert into paying customers?
2. How can the company prioritize and allocate resources to high-conversion leads?
3. What marketing and sales strategies can be tailored to specific lead segments to improve conversion rates?
4. How can the lead management process be streamlined to enhance effectiveness?

The goal of the project is to provide actionable insights that enable the company to make informed, data-driven decisions that drive business growth, improve conversion rates, and optimize marketing and sales efforts.

# Information About Dataset and Cleaning
* 9240 rows, 37 columns

* Removed Prospect ID and Lead Number columns. (35columns)

* 6 numerical columns and 29 categorical columns.

* Columns with more 40% of null values are removed: 

* Shape of dataset after removing null values: 9240 rows and 30 columns.

# Data Cleaning Steps

Numerical columns:

* Numerical columns, such as total visits and page views per visit, were handled by imputing missing values with the median.
    Outliers were also addressed by replacing extreme values with the median.
  
Categorical columns:

* Missing values in categorical columns were imputed with a new category "Unknown." Categories with low occurrences were grouped into a new category "Other" for better analysis and visualization.

Special Cases:

* Specific columns like "Select" in categorical fields were replaced with "Unknown" to reflect user inaction. 
    This step ensures accurate interpretation of the data.

# Insights from EDA


