# SQL.BellaBeat
Google Case Study: Bellabeat Smart Device Usage 
#

## Quick Links:

### Data Source: [Bellabeat Kaggle Dataset](https://www.kaggle.com/datasets/arashnic/fitbit/data)
### SQL Code: 
### Tableau Public:

## Introduction

This case study is part of the Google Data Analytics Professional Certificate program. As part of the Capstone Project, the following objective is to be completed.

## Objective 
You work on the marketing analyst team at Bellabeat, a high-tech firm specializing in health-centric products for women. The team's primary objective is to look into consumer usage patterns of smart devices, extracting valuable insights that will shape Bellabeat's marketing approaches. You have been tasked to focus on one of Bellabeat's products and analyze smart device data to gain insight into how consumers are using the devices. The findings and strategic recommendations derived from this analysis are slated for presentation to Bellabeat's executive team, with the aim of informing and enhancing the company's market positioning strategies. This project explores the company's opportunities for growth in the expansive global smart device market.

**Key Stakeholders:** 

- Urška Sršen: Bellabeat's cofounder and Chief Creative Officer
- Sando Mur: Mathematician and Bellabeat’s co-founder
- Bellabeat's Marketing Analytics team

**Questions to explore for the analysis:**

- What prevailing patterns can be identified in the utilization of smart devices?
- In what ways might these identified patterns be relevant to Bellabeat's clientele?
- How can these trends be leveraged to refine and enhance Bellabeat's marketing approaches?

## Tools used in Analysis
- Data Cleaning: Microsoft Excel 
- Data Analysis: Microsft SQL Server 
- Visualization: Tableau Public

## Data Analysis Process
We will be using the 6 phases of the data analysis process: Ask, Prepare, Process, Analyze, Share and Act.

## Step 1: Ask 
Bellabeat's Time product tracks the users activity, sleep, and stress. To address the business task of analyzing how users utilize the Time smart device, the following key findings will help guide the analysis:

- Acitivity Level by Users 
- Amount of Calories and Distance per Day
- Average Steps per Hour
- Total Steps and Total Distance by ID 
- Average Steps per ID and Average Hours of Sleep 
- Average steps per day of the week in relation to 10,000 step recommendation
- Average sleep per day in relation to recommended amount of 8 hours 

## Step 2: Prepare

The data for this analysis is sourced from a public dataset available on [Kaggle](https://www.kaggle.com/datasets/arashnic/fitbit). The original dataset includes 18 files containing detailed information about daily activity, sleep, weight, calories, and intensities. The dataset is structured in a combination of long and wide format, with each file containing specific information related to different aspects of smart device usage. It is important to note that the data is not from Bellabeat itself, therefore bias or data credibility may be an issue (but since this is a case study, I think we'll be ok). Our analysis will focus on the following datasets: 

- Daily_Activity
- Hourly_Steps
- Daily_Steps
- Daily_Sleep
- Weight

## Limitations 

- Sample size: The data contains only 33 participants, which may result in sampling bias. The Weight Dataset only has 8 participants. 
- Outdated: The dataset contains data from a two month period in 2016, April and May. A larger timeframe may be more representative of actual trends. 
- Limited: No demographic information provided, including age, or location. This information could be beneficial for marketing purposes to target specific customers.

### Process:

During the process phase, the data cleaning steps were carried out in Microsoft Excel. The following actions were performed:
- **Removed Unused Datasets:**  Daily_activity already included 'daily_steps', 'daily_calories' and 'daily_intensities', so they were removed. All minutes files were also removed as they were not needed for this analysis.
- **Removed Unused Columns in 'Daily Activity':** 'SedentaryActiveDistance' was removed.
- **Removed Unused Columns in 'Weight Dataset':** Only 2 entries for the column labeled 'Fat', column removed. Column labeled 'isManualReport', removed.  
- **Seperate 'Activity_Hour' Column in 'Hourly_Steps':** Used Text-to-columns with a fixed width to seperate time from date. Changed Activity Hour column to Activity_Date, changed format to short date.  
- **File Renaming:** Changed file names to uniform naming conventions to ensure consistency.
- **Check Data Type:** All columns with the exception of 'ActivityDate' were converted to numeric values.
- **Check for Missing Values:** 77 rows were removed with 0 entries for Total Daily Steps. 
- **Check for Blanks:** The data set was checked for incomplete or blank values in all columns. Some data, particularly 'steps_per_day', have 0 value entries, these rows were kept and removed from analysis with a > 0 formula in SQL.
- **Validated Column Values:** All column values in the respective datsets were valited using filter.


### Analyze:

During the Analyze phase, our objective is to explore the dataset thoroughly, revealing valuable insights and addressing significant discoveries pertaining to the usage of the Time product. Our primary emphasis lies in the data received from the product, focusing on the users daily activity, sleep, steps, and weight. This analysis should discover preferences and trends, with the ultimate goal of informing marketing strategies. Thorough examination of key findings were analyzed using Microsoft SQL Server.

#### 1. Categorizing users by activity level
- Sedentary - Less than 5000 steps a day
- Lightly active - Between 5000 and 7499 steps a day
- Fairly active - Between 7500 and 9999 steps a day
- Very active - More than 10000 steps a day

SQL Query: [Bellabeat Case Study SQL Code](https://github.com/Nick-Sierra/SQL.BellaBeat/blob/main/SQL%20Code)

Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/a4be5964-8e23-4f9c-9992-3cf3c8a37855)

Result: 

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/dc1396b6-932e-406c-83fc-70d067d63130)


#### 2. Amount of Calories and Distance per day 

SQL Query: [Bellabeat Case Study SQL Code](https://github.com/Nick-Sierra/SQL.BellaBeat/blob/main/SQL%20Code)

Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/57da74e7-26c3-4dee-a337-307d3cd83961)


#### 3. Average Steps per Hour 

SQL Query: [Bellabeat Case Study SQL Code](https://github.com/Nick-Sierra/SQL.BellaBeat/blob/main/SQL%20Code)

Result: 0 for the hour of the day represents 12:00 AM

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/a782906a-f340-45df-9ca0-0871262e22c9)


#### 4. Percent of time spent sleeping vs lying in bed 

SQL Query: [Bellabeat Case Study SQL Code](https://github.com/Nick-Sierra/SQL.BellaBeat/blob/main/SQL%20Code)

Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/ef944757-2890-4bce-ac8a-32c115d91eab)


#### 5. Average steps per ID and Average Hours of Sleep 

SQL Query: [Bellabeat Case Study SQL Code](https://github.com/Nick-Sierra/SQL.BellaBeat/blob/main/SQL%20Code)

Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/2be6b562-76e7-4039-809e-48695805ec4d)


#### 6. Do the average steps per day meet the 10,000 step recomendation   

SQL Query: [Bellabeat Case Study SQL Code](https://github.com/Nick-Sierra/SQL.BellaBeat/blob/main/SQL%20Code)

Result: Total steps > 0 was added to exclude entries with 0 steps per day 

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/d462e72c-938e-4afa-b6c6-30c5d549957b)


#### 7. Does the average sleep per day meet the recommended 8 hours 

SQL Query: [Bellabeat Case Study SQL Code](https://github.com/Nick-Sierra/SQL.BellaBeat/blob/main/SQL%20Code)

Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/af84da4c-d6d3-4eb5-b991-b1880777573d)


#### 8. Is there a relation between number of steps taken and hours of sleep?

SQL Query: [Bellabeat Case Study SQL Code](https://github.com/Nick-Sierra/SQL.BellaBeat/blob/main/SQL%20Code)

Result: 

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/c7868422-d592-42bd-ba7d-126f69f7c165)


#### 9. Average hours of sleep by active category 

SQL Query: [Bellabeat Case Study SQL Code](https://github.com/Nick-Sierra/SQL.BellaBeat/blob/main/SQL%20Code)

Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/9f654716-a960-4064-90b8-e957cecee19d)


### Share: 

After processing the valuable insights, we will now explore explanatory visualizations that showcase user's healthy daily activities and correlate key parameters using  The appealing visualizations are provided below:

#### 1. Categorizing users by activity level
The pie chart analysis indicates that within our user base, 30.3% are 'Fairly Active', taking 7,500 to 9,999 steps daily. 'Very Active' users, exceeding 10,000 steps, account for 21.2%, while 'Lightly Active' users represent 27.3% with 5,000 to 7,499 steps. A significant portion, 21.2%, are 'Sedentary', with less than 5,000 daily steps. These findings highlight a potential area for encouraging increased physical activity among the less active user segments.

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/40eb829d-5d58-40de-a87d-539b3719811d)

#### 2. Amount of Calories and Distance per day 
The dual-axis chart presents the amount of calories burned and total distance covered by users across different days of the week. The data shows that activity levels, in terms of total distance and calories burned, fluctuate throughout the week. There's a noticeable dip on Sunday and Friday, with a subsequent increase on Monday, peaking on Tuesday, and then a general decline towards the end of the week. This information can be used to understand users' activity patterns, possibly to target communications and challenges to increase activity levels on the lower activity days.

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/2624100b-64b9-4b29-8a39-624adbb9a4bb)


#### 3. Average Steps per Hour 
The data shows the average number of steps taken by users for each hour of the day. The peak activity appears to be in the late afternoon and early evening hours, specifically around 5 PM to 7 PM, with the highest average steps per hour at 599.2 around 7 PM. There's also a significant increase in steps in the early morning, around 6 AM, which may correspond with a common time for morning workouts or commutes.

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/6963b5d5-4383-44cc-9759-08e63fe9eb3a)


#### 4. Percent of time spent sleeping vs lying in bed 
The scatter plot illustrates a trend between the average total hours spent asleep and the average time spent in bed not sleeping. Each point represents the aggregated data for an individual user, showing their sleep efficiency. The upward-sloping trend line suggests that as users sleep for more total hours, they also tend to spend more time in bed not sleeping. The bar chart breaks down sleep efficiency ((Total Minutes Asleep / Total Time in Bed)*100) by day of the week. It appears that sleep efficiency does not vary by much across the week, with Sunday and Tuesday having the least efficient sleep habits. 

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/a05c9b41-c3b2-44e9-b271-a244d5e02bde)

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/0d36d864-5154-4fa3-b2f9-f51c4caa4c2b)


#### 5. Average steps per ID and Average Hours of Sleep  
The scatter plot indicates a negative correlation between users' average daily steps and average hours of sleep. Individuals with higher step counts tend to have fewer hours of sleep. This trend could imply that highly active users may experience shorter sleep durations. This suggests that users who are very active might benefit from features that help to manage or improve sleep quality.

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/65bac921-dfe3-4142-848b-01455bc9e045)


#### 6. Do the average steps per day meet the 10,000 step recommendation   
The scatter plot illustrates the daily step counts for individual users, with each dot representing a user's average steps. The majority of users fall short of the recommended 10,000 steps per day, as most data points are situated to the left of the recommended 10,000-step mark. This visualization serves as a clear indicator that there is significant room for improvement in physical activity among the user base. 

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/18b38151-34a5-49b5-a905-5711f245b532)


#### 7. Does the average sleep per day meet the recommended 8 hours 
The scatter plot depicts individual users' average total hours of sleep, with the 8-hour mark highlighted as the recommended sleep duration. 88% of users sleep less than the recommended 8 hours, signaling an area where Bellabeat could focus on promoting better sleep habits and wellness features that encourage sufficient rest.

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/66ecfb6d-5acd-4b99-b054-5e2ff8aa47df)


#### 8. Average hours of sleep by active category 
The bar chart categorizes users by their level of activity and shows the corresponding average hours of sleep for each group. Notably, 'Lightly Active' users average the most sleep at 7.1 hours, closely followed by 'Fairly Active' users at 6.9 hours. 'Sedentary' users get 6.3 hours of sleep on average, while 'Very Active' users get significantly less sleep, averaging only 4.7 hours. This information further suggests a potential inverse relationship between high activity levels and sleep duration, with the most active users sleeping the least. 
![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/215860a4-8cf3-4335-9806-ec1c87b31073)


### Act Phase 

#### Key Takeaways

Based on the findings of this analysis, some key takeaways can be derived:

- Activity Level Insights: Users fall into distinct categories based on activity, with a notable portion of the user base not meeting the recommended daily steps. Engagement in physical activity varies throughout the week, peaking midweek.

- Sleep Patterns: There's a varied distribution of sleep efficiency, with some days showing higher sleep quality than others. Most users do not meet the recommended 8 hours of sleep, with 'Very Active' users sleeping the least on average.

- Activity vs. Sleep Correlation: A negative correlation is observed between activity levels and sleep duration, indicating that more active users tend to sleep less.

- Steps Recommendation Achievement: The analysis indicates that users rarely meet the 10,000 daily step recommendation, suggesting an opportunity for interventions to increase activity levels.

- Sleep Efficiency: Users show different sleep efficiency rates throughout the week, with midweek days typically showing higher efficiency. This suggests a potential focus for improving sleep-related features in Bellabeat products.

- Opportunities for Bellabeat: The insights from the data analysis present opportunities for Bellabeat to tailor their health-centric products to encourage more consistent activity levels and better sleep habits among their users. This could include developing targeted features or campaigns to motivate users to increase daily activity and improve sleep quality.
 
#### Recommenations: 

Drawing from the insights gained from the Bellabeat study, the following strategic recommendations are proposed for the business:

- Targeted Step Count Increase Programs: Introduce initiatives within the Bellabeat app that specifically aim to help users reach the 10,000 steps daily recommendation. This could be through incremental step goals, virtual group walks, or step-based challenges with milestones.

- Data-Driven Sleep Tools: Given the shortfall in sleep hours among users, especially the 'Very Active', develop advanced sleep tracking and analysis tools. These tools could provide feedback on sleep patterns and offer personalized tips to improve sleep duration and quality.

- Midweek Activity Engagement: Deploy midweek motivational pushes through the app, as activity levels tend to be higher during this time. This could involve midweek check-ins or encouragement to maintain or increase activity levels to capitalize on the existing user behavior trend.

- Weekend Activity Incentives: To address the dip in activity over the weekends, design weekend-specific challenges or family-friendly activities that can incentivize users to be more active during these days.

- Negative Correlation Mitigation: For users demonstrating a negative correlation between high activity and sleep duration, provide education and resources on the importance of recovery and rest. This could be through in-app articles, notifications, or integration with relaxation and meditation guidance.

- Enhanced Visualization Tools: Improve the app's data visualization capabilities to make users more aware of their activity and sleep trends. Providing users with easy-to-understand graphs and charts could help them make better health decisions.

By focusing on these areas, Bellabeat can not only improve user engagement and satisfaction but also solidify its position as a partner in users' health journeys, ultimately driving brand loyalty and growth.


