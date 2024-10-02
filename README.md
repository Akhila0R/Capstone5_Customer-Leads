# Capstone5_Customer-Leads
## Table of Contents
- [Problem Statement](#problem-statement)
- [Information About Dataset and Cleaning](#information-about-dataset-and-cleaning)
- [Data Cleaning Steps](#data-cleaning-steps)
- [Insights from EDA](#insights-from-eda)
- [Encoding with ONE HOT ENCODER](#encoding-with-one-hot-encoder)
- [Handling Imbalance in Target Variable](#handling-imbalance-in-target-variable)
- [Feature Scaling using MINMAX Scaler](#feature-scaling-using-minmax-scaler)
- [Visualizing Model Scores](#visualizing-model-scores)
- [Feature Importance](#feature-importance)
- [Important Features](#important-features)
- [Which leads are most likely to convert into paying customers](#which-leads-are-most-likely-to-convert-into-paying-customers)
- [How can the platform prioritize and allocate resources to leads with the highest conversion](#how-can-the-platform-prioritize-and-allocate-resources-to-leads-with-the-highest-conversion)
- [What marketing and sales strategies can be tailored to specific lead segments](#what-marketing-and-sales-strategies-can-be-tailored-to-specific-lead-segments)
- [How can the lead management process be streamlined and made more effective](#how-can-the-lead-management-process-be-streamlined-and-made-more-effective)
## Problem Statement
The Edu-Tech company is seeking to improve its customer acquisition process, optimize marketing strategies, and enhance lead conversion rates by leveraging its customer data. The objective is to analyze this data to gain insights into customer behaviors, preferences, and conversion patterns. These insights will be used to prioritize leads with the highest likelihood of conversion, refine marketing and sales strategies, and optimize resource allocation.
Key questions to address include:

1. Which leads are most likely to convert into paying customers?
2. How can the company prioritize and allocate resources to high-conversion leads?
3. What marketing and sales strategies can be tailored to specific lead segments to improve conversion rates?
4. How can the lead management process be streamlined to enhance effectiveness?

The goal of the project is to provide actionable insights that enable the company to make informed, data-driven decisions that drive business growth, improve conversion rates, and optimize marketing and sales efforts.

## Information About Dataset and Cleaning
* 9240 rows, 37 columns

* Removed Prospect ID and Lead Number columns. (35columns)

* 6 numerical columns and 29 categorical columns.

* Columns with more 40% of null values are removed: 

* Shape of dataset after removing null values: 9240 rows and 30 columns.

## Data Cleaning Steps

Numerical columns:

* Numerical columns, such as total visits and page views per visit, were handled by imputing missing values with the median.
    Outliers were also addressed by replacing extreme values with the median.
  
Categorical columns:

* Missing values in categorical columns were imputed with a new category "Unknown." Categories with low occurrences were grouped into a new category "Other" for better analysis and visualization.

Special Cases:

* Specific columns like "Select" in categorical fields were replaced with "Unknown" to reflect user inaction. 
    This step ensures accurate interpretation of the data.

## Insights from EDA

1. Conversion Rates – Target variable:
* 0 indicates Not converted.
* 1 indicates Converted.
* 38.5% were successfully converted; while 61.5% were not.

2. Total Visits:
* Most people visit for 0 and 2 to 5 times.
* Leads with visits (0, 2, 4, 5) show high conversion chances.
* Equal chances of conversions beyond 7 visits.

3. Time Spent On Website:
* Most people spend 0 to 49 seconds.
* Time > 700 seconds indicates higher conversion likelihood.

4. Page Views per Visit:
* People like to visit avg. of 0-6 pages.
* Equal conversion chances for 0-6 average page views.

5. Lead Origin:
* Lead origin from Landing page submission and API is higher.
* Conversion is higher for lead origin from Landing Page, Lead Add Form and API.

6. Lead Source:
* 98% of leads from Lead Source as  Wellingak website were converted into customers.
* Lead source Unknown and Reference has 80% and 90% conversion.
* Google, Direct Traffic, Organic Search and Olark Chat also has good chances of being converted into customers. 

7. Do Not Email:
* 92% of leads choose not to email them. 40% among them were still converted.
* 16% of customers who choose to email them got converted.

8. Do Not Call:
* 99.97% of people chose not to call them. 38.5% of them were still converted.
* The two customers who opted for calling them were converted.

10. Updates on Course contents and payment through cheque:
* All leads have opted not get updates on courses, DM content, Supply Chain Content and not to pay through cheque.
* 38.5% of them got converted anyways.

11. A free copy of Mastering the Interview:
* 31.3% of leads have opted to get a free copy of Mastering the Interview. 35% of them got converted.
* 39% of leads who have not opted for free copy have been converted.

12. Last Activity:
* Email Opened and SMS Sent have more distribution and SMS Sent category has higher chances of getting converted than Email Opened.
* Unknown, Other, Had a Phone conversation categories have more than 70% chances of getting converted.

13. Last Notable Activity:
* Distribution is more towards ‘Modified’, ‘Email Opened and ‘SMS Sent’.
* 69% of last notable activity as SMS Sent got converted.
* 92% of leads with last notable activity as Had a Phone Conversation got converted.

14. Country:
* Higher distribution in India and Unknown categories.
* Unknown and Singapore show >40% conversion chances. 

15. City:
* Distribution is more towards Unknown and Mumbai.
* All categories except Tier 2 cities have 39 to 43% of chances to get converted.

16. Specialization:
* Distribution is high in Unknown Category.
* More than 40% of conversions in Finance, Business, Operations, Marketing, Supply Chain, Human Resource, Hospitality, Banking and Finance  and Healthcare Management.

17. Current occupation:
* Distribution is high in Unemployed and Unknown categories.
* 91% of working professionals were converted. All housewives were converted.
* Businessman and other categories have more than 60% of chances to get converted.

18. Digital Advertising: 38.5% of leads who have not seen any kind of ads were converted.
* Only 0.2% (14) of leads have seen the ad in SEARCH and have low chances (35%) of getting converted.
* 4 among 9240 leads have seen Digital Advertisements. Only 1 among them was converted.
* Only 1 among 9240 leads have seen Ads in X Education Forums.

19. Word Of Mouth:38.5% of leads who have not seen any kind of ads were converted.
* 7 among 9240 leads have come through recommendations. 5 among them were converted.

20. Traditional Media:38.5% of leads who have not seen any kind of ads were converted.
* 100% of leads have not seen ads in Magazines.
* Only 2 in 9240 leads have seen Ads in Newspaper Article.
* Only 1 among 9240 leads have seen Ads in Newspaper.

21. What matters most to you in choosing a course:
* Better career prospects and Unknown categories has more distribution.
* Better career prospects have higher chances of converting to customers.

22. Tags:
* Leads tagged as ‘Will revert after reading the email’, ‘Lost to EINS’ and ‘Closed by Horizzon’ have very high chances of getting converted.

23. Lead Profile:
* 74% of values in Unknown category.
* Lead profiles named as ‘Potential Lead’, ‘Lateral Student’ and ‘Dual Specialization Student’ have very high chances of getting converted.

## Encoding with ONE HOT ENCODER
* In this project, One-Hot Encoding was applied to handle categorical features. The dataset initially contained 30 columns, including 26 categorical variables. 
* One-Hot Encoding converts each categorical feature into multiple binary columns, where each unique category within a feature is represented as a new column with values of either 0 or 1. 
* This transformation ensures that the categorical variables are represented in a machine-readable format without introducing any ordinal relationships between categories.
* The shape of the dataset before encoding was (9240, 30). After applying One-Hot Encoding, the shape of the dataset increased to (9240, 147) due to the expansion of categorical features into individual binary columns.

## Handling Imbalance in Target Variable
* The dataset initially exhibited class imbalance in the target variable Converted, with the following distribution:
* 0 (Not Converted): 5679 instances
* 1 (Converted): 3561 instances
* To address this imbalance, the Synthetic Minority Over-sampling Technique (SMOTE) was applied. SMOTE generates synthetic examples for the minority class by interpolating between existing instances, effectively balancing the classes without simply duplicating data points.
* After applying SMOTE, the target class distribution was balanced to:
* 0 (Not Converted): 5679 instances
* 1 (Converted): 5679 instances
* This resampling ensures that the model can better learn patterns from both classes, reducing bias towards the majority class during training.

## Feature Scaling using MINMAX Scaler
* To normalize the range of the features, MinMax Scaler was applied to the dataset. This scaling technique transforms each feature to a given range, typically between 0 and 1, by subtracting the minimum value and dividing by the range (maximum value - minimum value).
* MinMax Scaling ensures that all features contribute equally to the model, preventing features with larger values from dominating the learning process. It is especially useful when the dataset includes features with different units or magnitudes, ensuring that no feature disproportionately influences the model's performance.

## Visualizing Model Scores
* After performing X, y split and Train, Test Split we run the model scores for various models like Logistic Regression, Random Forest,etc.
* The accuracy of test set for random forest model is 0.9525
ROC_AUC Score is 0.98
* Next Step is to perform Hyper Parameter Tuning by using GridSearchCV to derive the best Parameters for training the Random Forest Model.

## Feature Importance
* The top 15 important features in determining the target variable are as follows.
    *Tags_Will revert after reading the email
    * Total
    * _Time_Spent_on Website
    * Tags_Ringing
    * Last_Notable_Activity_SMS Sent
    * Lead_Profile_Potential Lead
    * Last_Activity_SMS Sent
    * What_is_your_current_occupation Working Professional
    * Tags_Closed by Horizzon
    * What_matters most_to you in_choosing a_course_Better Career Prospects
    * Lead _Origin_Lead Add Form
    * Tags_Lost to EINS
    * What _matters_most_to you in_choosing_a_course_Unknown
    * Tags _Unknown
    * What _is your _current_occupation_Unknown
    * Tags_Interested in other courses

## Important Features
* Tags :
    * Will revert after reading the email
    * Ringing
    * Closed by Horizzon
    * Lost to EINS
    * Unknown
    * Interested in Other Courses
*  Total Time Spent On website
* Last Activity – SMS Sent
* Lead Profile – Potential Lead
* Occupation- Working Professional, Unknown
* What matters the most in choosing the course: Better Career Prospects, Unknown
* Lead Origin- Lead Add Form

## Which leads are most likely to convert into paying customers
* Leads with 2 to 5 website visits or those who spent over 700 seconds on the website are more likely to convert.
* Landing Page submissions, API, and Lead Add Forms have a higher conversion rate.
* Lead Sources like References, Wellingak website, and Google yield higher conversions, with some sources like References converting 90% of leads.
* Customers who previously had a phone conversation or were tagged as ‘Will revert after reading the email’ have a 70%+ conversion rate.
* Working professionals and leads in specialized fields like Finance Management or Business Administration have high conversion chances. 

## How can the platform prioritize and allocate resources to leads with the highest conversion
* Prioritize leads who spent significant time on the website (especially more than 700 seconds).
* Focus resources on leads from trusted lead sources (e.g., Reference, Wellingak website).
* Leads tagged with positive follow-up statuses such as ‘Will revert after reading email’ should be prioritized.
* Resource allocation should focus on working professionals, specialized domain leads, and high-conversion last activities like SMS Sent or Phone Conversations.
* Avoid heavy investment in leads with fewer interactions (e.g., leads with only 1 page view or low time spent on the website). 

## What marketing and sales strategies can be tailored to specific lead segments
* High-conversion sources (e.g., Google, Reference) should receive targeted email marketing or follow-up calls to maximize conversion.
* Leads who prefer no emails or calls should be nurtured through SMS campaigns as the data shows SMS leads have higher conversion rates.
* Design marketing strategies that address leads' focus on better career prospects, as this was a key motivator for conversion.
* Tailor messaging for working professionals by highlighting career advancement opportunities, while housewives and businessmen should be targeted with flexible learning benefits.
* For leads in specialized domains like Healthcare Management or Finance, personalized course offerings can boost conversions. 

## How can the lead management process be streamlined and made more effective
* Segment leads based on lead origin and lead source to determine which channels produce higher-quality leads, allowing more focused efforts on high-converting channels.
* Automate follow-ups for leads with high-conversion tags like ‘Will revert after reading email’ or last activities such as SMS Sent or Phone Conversation, to minimize manual intervention.
* Use lead scoring systems that prioritize leads with multiple interactions (e.g., 2-5 website visits, more than 700s on the website) and those from high-conversion sources.
* Implement a nurturing funnel that escalates high-potential leads to a more personalized approach (e.g., offering phone consultations for leads with a history of successful conversions). 

