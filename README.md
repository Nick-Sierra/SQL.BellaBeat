# SQL.BellaBeat
Google Case Study: Bellabeat Smart Device Usage 
#

## Quick Links:

### Data Source: https://www.kaggle.com/datasets/arashnic/fitbit/data
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

SQL Query: 

SQL Query:

Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/a4be5964-8e23-4f9c-9992-3cf3c8a37855)

Result: 

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/dc1396b6-932e-406c-83fc-70d067d63130)


#### 2. Amount of Calories and Distance per day 

SQL Query: 

Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/57da74e7-26c3-4dee-a337-307d3cd83961)


#### 3. Average Steps per Hour 

SQL Query: 

Result: 0 for the hour of the day represents 12:00 AM

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/a782906a-f340-45df-9ca0-0871262e22c9)


#### 4. Percent of time spent sleeping vs lying in bed 

SQL Query: 

Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/ef944757-2890-4bce-ac8a-32c115d91eab)



#### 5. Average steps per ID and Average Hours of Sleep 
SQL Query: 
Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/2be6b562-76e7-4039-809e-48695805ec4d)



#### 6. Do the average steps per day meet the 10,000 step recomendation   

SQL Query: 

Result: Total steps > 0 was added to exclude entries with 0 steps per day 

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/d462e72c-938e-4afa-b6c6-30c5d549957b)


#### 7. Does the average sleep per day meet the recommended 8 hours 

SQL Query: 

Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/af84da4c-d6d3-4eb5-b991-b1880777573d)


#### 8. Is there a relation between number of steps taken and hours of sleep?

SQL Query: 

Result: 

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/c7868422-d592-42bd-ba7d-126f69f7c165)


#### 9. Average hours of sleep by active category 

SQL Query: 

Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/9f654716-a960-4064-90b8-e957cecee19d)


### Share: 

After processing the valuable insights, we will now explore explanatory visualizations that showcase user's healthy daily activities and correlate key parameters using  The appealing visualizations are provided below:

#### 1. Categorizing users by activity level
The analysis of the proportion of calories per distance by day reveals interesting insights into users activity level. Specifically, it is observed that Sundays exhibit a relatively high proportion of calories burned per distance compared to other days of the week. 


#### 2. Amount of Calories and Distance per day 
The visualization showcasing the average steps taken per hour reveals interesting patterns in users activity throughout the day. It is evident that the highest average number of steps is recorded during the 6 p.m. hour. This finding suggests that users are more active and tend to engage in higher levels of physical activity during evening time.

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/2624100b-64b9-4b29-8a39-624adbb9a4bb)


#### 3. Average Steps per Hour 
This key finding highlights the relationship between total steps and total distance covered by individual users. The analysis reveals that user ID '8877689391' recorded the highest number of steps, totaling 497,241, and covered a distance of 409.4 units. This indicates that this particular user has been highly active, taking a significant number of steps and covering a considerable distance.

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/6963b5d5-4383-44cc-9759-08e63fe9eb3a)


#### 4. Percent of time spent sleeping vs lying in bed 
The calculated field for this finding devides the TotalMinutesAsleep column with the TotalTimeinBed column * 100 to receive the percent of time spent sleeping vs lying in bed. 

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/11e9c653-362e-49bd-a5c3-410f9c216c9c)

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/b03912a7-4ea6-4e5b-99d9-4a84f1bdbab5)


#### 5. Average steps per ID and Average Hours of Sleep  

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/7ef77b92-1199-4727-8a81-e963ec36633a)


#### 6. Do the average steps per day meet the 10,000 step reccomendation   

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/18b38151-34a5-49b5-a905-5711f245b532)



#### 7. Does the average sleep per day meet the recommended 8 hours 

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/66ecfb6d-5acd-4b99-b054-5e2ff8aa47df)


#### 8. Is there a relation between number of steps taken and hours of sleep?

#### 9. Average hours of sleep by active category 


### Act Phase 

#### Key Takeaways

Based on the findings of this analysis, some key takeaways can be derived:

- Users find Sunday as a day when actively prioritize their health and engage in physical activities. It further suggests that people may intentionally select one day of the weekend to focus on maintaining an active lifestyle, while allocating the other day for more sedentary pursuits.
- The peak in average steps per hour at 5 to 6 PM, indicating that individuals are most active in evening.
- Despite the positive correlation between steps and active minutes, the majority of users in the dataset still spend a significant amount of time in a sedentary state, highlighting the need to promote more physical activity and reduce sedentary behavior.
-  The analysis of sleep and activity minutes over the week indicates that users are meeting the minimum sleep standard of 7 hours. However, despite achieving sufficient sleep, their active time remains relatively low, with a significant portion of the day spent in a sedentary state
 
#### Recommenations: 
Based on the key findings of the Bellabeat smart devices usage, here are some recommendations for the business:

- **Personalized Activity Reminders:** Develop a feature within the Bellabeat smart devices that provides personalized activity reminders to users. These reminders can be based on their specific activity patterns and can encourage them to engage in more active behaviors throughout the day.

- **Sleep Optimization Guidance:** Offer sleep optimization guidance through the Bellabeat smart devices. This could include providing recommendations on sleep duration and quality, as well as tips for improving sleep habits. The goal is to help users establish healthy sleep routines and maximize their sleep benefits.

- **Active Time Tracking:** Enhance the activity tracking capabilities of the Bellabeat smart devices by providing users with detailed insights into their active time distribution throughout the day. This can help users understand their activity patterns and motivate them to increase their active minutes by incorporating not only steps but about cycling, yoga, walking etc. 

- **Activity Challenges and Rewards:** Implement activity challenges and rewards within the Bellabeat app. This can create a sense of competition and motivation among users to achieve their activity goals. Rewards can include virtual badges, discounts on Bellabeat products, or access to exclusive content.

By implementing these recommendations, Bellabeat can enhance the user experience, increase engagement with the smart devices, and further establish itself as a leading provider of health and wellness solutions.


## Visualization 


