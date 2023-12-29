# SQL.BellaBeat
Google Case Study: BellaBeat Smart Device Usage 
#
_The case study follows the six step data analysis process:_

## Quick Links:

### Data Source: 
### SQL Code: 
### Tableau Public:

## Introduction

This case study is part of the Google Data Analytics Professional Certificate program. As part of the Capstone Project, the following objective is to be completed.

## Objective 
You work on the marketing analyst team at Bellabeat, a high-tech firm specializing in health-centric products for women. The team's primary objective is to delve into consumer usage patterns of smart devices, extracting valuable insights that will shape Bellabeat's marketing approaches. You have been tasked to focus on one of Bellabeat's products and analyze smart device data to gain insight into how consumers are using the devices. The findings and strategic recommendations derived from this analysis are slated for presentation to Bellabeat's executive team, with the aim of informing and enhancing the company's market positioning strategies. This project explores the company's opportunities for growth in the expansive global smart device market.

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
In order to adequately analyze bellabeat data and to answer the key business questions and make recommendations, we will use the following 6 data analysis phases: Ask, Prepare, Process, Analyze, Share and Act.

## Step 1: Ask 
To address the business task of analyzing how users utilize the time smart device, the following key findings will guide the analysis:

- Proportion of Calories per Distance by Day
- Average Steps per Hour
- Total Steps & Total Distance by ID
- Maximum Sleep Duration (in hours) by Day
- Correlation of Steps with Active Minutes
- Correlation of Sleep with Active Minutes by Day

## Step 2: Prepare

The data for this analysis is sourced from a public dataset available on [Kaggle](https://www.kaggle.com/datasets/arashnic/fitbit). The dataset includes 18 files containing detailed information about daily activity, sleep, weight, calories, and intensities. The dataset is structured in a combination of long and wide format, with each file containing specific information related to different aspects of smart device usage. It is important to note that the data is not from Bellabeat itself, there may be potential issues with bias or credibility. Our analysis will focus on the following datasets: 

- Daily_Activity
- Hourly_Steps
- Daily_Steps
- Daily_Sleep
- Weight

## Limitations 

- Sample size: The data contains only 33 participants, which may result in sampling bias. The Weight Dataset only has 8 participants. 
- Outdated: The dataset contains data from a two month period in 2016, April and May. A larger timeframe may be more representative of actual trends. 
- Limited: No demographic information provided, including age, or location. This information could be beneficial for marketing purposes to target specific customers.

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/7a555b70-86dc-47b1-8fca-310acbd56bc4)

#### Cleaning in Excel:

The following considerations were observations and updated to clean data effectively:
- **Removed Unused Datasets:**  Daily_activity already included 'daily_steps', 'daily_calories' and 'daily_intensities', so they were removed. All minutes files were also removed as they were not needed for this analysis.
- **Removed Unused Columns:** SedentaryActiveDistance was removed.
- **Removed Unused Columns Weight Dataset:** Only 2 entries for the column labeled Fat, removed column. Column labeled isManualReport, removed.  
- **Seperate Activity Hour Column in Hourly_Steps:** Used Text to columns with a fixed to seperate time from date. Changed Activity Hour column to Activity_Date, changed format to short date.  
- **File Renaming:** Changed file names to uniform naming conventions to ensure consistency.
- **Check Data Type:** All columns with the exception of ActivityDate were converted to numeric value.
- **Check duplicates:** Duplicate values were identified from two files and removed using 'Remove Duplicates'.
- **Check for Missing Values:** 77 rows were removed with 0 entries for Total Daily Steps. 
- **Check for Blanks:** The data set was checked for incomplete or blank values in all columns.
- **Validate Column Values:** All column values in the respective files were valited using filter.
- **Sorting the Table:** The table was sorted in ascending order based on the 'Date' column.

### Process Phase:
During this phase, a thorough examination of the key findings related to how users utilize Bellabeat smart devices was conducted using Microsoft SQL Server.

#### 1. Catagorizing users by activity level
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


#### 4. Total Steps & Total Distance by ID

SQL Query: 

Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/86a12c47-3d4a-4628-899c-0f79fd417100)


#### 5 Average steps per ID and Average Hours of Sleep 
SQL Query: 
Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/2be6b562-76e7-4039-809e-48695805ec4d)



#### 5. Do the average steps per day meet the recommended 10,000 step reccomendation   

SQL Query: 

Result: Total steps > 0 was added to exclude entries with 0 steps per day 

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/d462e72c-938e-4afa-b6c6-30c5d549957b)


#### 6. Does the average sleep per day meet the recommended 8 hours 

SQL Query: 

Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/af84da4c-d6d3-4eb5-b991-b1880777573d)


#### 7. Is there a Correlation between number of steps taken and hours of sleep?

SQL Query: 

Result: 

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/c7868422-d592-42bd-ba7d-126f69f7c165)


#### 7. Average hours of sleep by active category 

SQL Query: 

Result:

![image](https://github.com/Nick-Sierra/SQL.BellaBeat/assets/149681943/9f654716-a960-4064-90b8-e957cecee19d)


### Analyze Phase: 

After processing the valuable insights, we will now explore explanatory visualizations that showcase user's healthy daily activities and correlate key parameters using  The appealing visualizations are provided below:

#### 1. Proportion of Calories per Distance by Day:
The analysis of the proportion of calories per distance by day reveals interesting insights into users activity level. Specifically, it is observed that Sundays exhibit a relatively high proportion of calories burned per distance compared to other days of the week. 


#### 2. Average Steps per Hour 
The visualization showcasing the average steps taken per hour reveals interesting patterns in users activity throughout the day. It is evident that the highest average number of steps is recorded during the 6 p.m. hour. This finding suggests that users are more active and tend to engage in higher levels of physical activity during evening time.



#### 3. Total Steps & Total Distance by ID
This key finding highlights the relationship between total steps and total distance covered by individual users. The analysis reveals that user ID '8877689391' recorded the highest number of steps, totaling 497,241, and covered a distance of 409.4 units. This indicates that this particular user has been highly active, taking a significant number of steps and covering a considerable distance.



#### 4. Maximum Sleep Duration (in hours) by Day

The sleep duaration was categorized in days, and it is identified that maximum sleep duraton is found to be 13 'hours' on 'Monday'. This finding suggests that users tend to have longer sleep periods on Mondays compared to other days of the week.




#### 5. Correlation of Steps with Active Minutes (Very Active and Sendetary Minutes)

The analysis reveals a clear correlation between total steps, very active minutes, and sedentary minutes. As the total steps increase, the very active minutes also tend to increase, while the sedentary minutes decrease. This suggests that individuals who take more steps engage in more intense physical activity and spend less time in a sedentary state. These findings align with the recommendations of the Centers for Disease Control and Prevention (CDC), which suggests engaging in at least 30 minutes of moderate physical activity every day for optimal health. However, the data indicates that the majority of users in the dataset spend a considerable amount of time in a sedentary state, with relatively low levels of very active minutes.




#### 6. Correlation of Sleep with Each Active Minutes by day

The analysis of sleep and activity minutes over the week reveals that, on average, users spent approximately 6.98 hours sleeping, 13.31 hours in a sedentary state, 3.33 hours in light activity, 0.27 hours in fairly active moments, and 0.40 hours in very active periods.This highlights that users tend to spend a significant amount of time in sedentary behavior during the weekdays. Additionally, the data indicates that users allocates maximum time for sleep and have minimal engagement in activities.




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


