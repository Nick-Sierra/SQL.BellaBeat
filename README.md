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

## Limitations 

- Sample size: The data contains only 30 participants, which may result in sampling bias.
- Outdated: The dataset contains data from a two month period in 2016, April and May. A larger timeframe may be more representative of actual trends. 
- Limited: No demographic information provided, including age, or location. This information could be beneficial for marketing purposes to target specific customers.

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

### Prepare Phase:

The data for this analysis is sourced from a public dataset available on [Kaggle](https://www.kaggle.com/datasets/arashnic/fitbit). It comprises of 18 files containing detailed information about daily activity, sleep, weight, calories, and intensities. The dataset is structured in a combination of long and wide format, with each file containing specific information related to different aspects of smart device usage. It is important to note that the data is not from Bellabeat itself, there may be potential issues with bias or credibility.  Furthermore, it is worth mentioning that the dataset is not up to date, encompassing data only for the months of April and May in 2016. Therefore, the analysis may not fully reflect the most current trends in smart device usage. Additionally, it's important to acknowledge that the dataset lacks information about the Spring product and the Bellabeat app, thereby limiting the scope of the analysis to the Time smart device.

![Capture](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/9bdef8a3-95a7-47d2-b064-cf43254f199f)

### Prepare Phase: 

#### Cleaning in Excel:

The following considerations were observations and updated to clean data effectively:
- **Removal of Unwanted Tables:** As 'daily_steps', 'daily_calories' and 'daily_intensities' table were part of daily_activity file, also it was validated using MATCH function. Therefore, unwanted files that will not be part of anlysis were removed.
- **Rename File:** Proper naming conventions were applied to maintain data integrity.

![removed files](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/e7af6943-7c58-4f87-8077-65158be29b7d)

- **Check Data Type:** Data type of relevant columns, such as, TotalSteps, TotalDistance, VeryActiveMinutes, LittleActiveMinutes, FairlyActiveMinutes and SedentaryMinutes were converted to numeric value.
- **Check duplicates:** Duplicate values were identified from two files and removed using 'Remove Duplicates'.
- **Check for Blanks:** The data set was checked for incomplete or blank values in all columns.
- **Validate Column Values:** All column values in the respective files were valited using filter.
- **Sorting the Table:** The table was sorted in ascending order based on the 'Date' column.

### Process Phase:
During this phase, a thorough examination of the key findings related to how users utilize Bellabeat smart devices was conducted using Microsoft SQL Server.

#### 1. Proportion of Calories per Distance by Day:

SQL Query: [Bellabeat Case Study Complete Code](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/blob/main/Bellabeat%20Case%20Study%20-%20Complete%20Code.sql)

Result:

![calories distance per weekday](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/c54d2447-73e9-4ab8-ad7f-667a868a3d33)

#### 2. Average Steps per Hour 

SQL Query: [Bellabeat Case Study Complete Code](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/blob/main/Bellabeat%20Case%20Study%20-%20Complete%20Code.sql)

Result: 

![steps per hour](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/2b878c84-5c11-463e-8d03-84cf5d4aee65)

#### 3. Total Steps & Total Distance by ID

SQL Query: [Bellabeat Case Study Complete Code](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/blob/main/Bellabeat%20Case%20Study%20-%20Complete%20Code.sql)

Result:

![steps vs distances](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/19745eca-1d8c-44e2-a074-e5e3dee794f4)

#### 4. Maximum Sleep Duration (in hours) by Day

SQL Query: [Bellabeat Case Study Complete Code](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/blob/main/Bellabeat%20Case%20Study%20-%20Complete%20Code.sql)

Result: 

![sleep per weekday](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/dc270fe6-30bb-44b0-969e-efe597e5e572)

#### 5. Correlation of Steps with Active Minutes

SQL Query: [Bellabeat Case Study Complete Code](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/blob/main/Bellabeat%20Case%20Study%20-%20Complete%20Code.sql)

Result: 

![image](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/9f80779b-0257-40b7-8106-4b6e68913f9e)


#### 6. Correlation of Sleep with Active Minutes by Day

SQL Query: [Bellabeat Case Study Complete Code](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/blob/main/Bellabeat%20Case%20Study%20-%20Complete%20Code.sql)

Result:

![sleep active minutes per day](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/aa1754d0-375b-43f3-9e4d-a55a020436f2)

### Analyze Phase: 

After processing the valuable insights, we will now explore explanatory visualizations that showcase user's healthy daily activities and correlate key parameters using [Tableau Public](https://public.tableau.com/views/BellaBeatSmartDeviceUsageDashboard/Dashboard2?:language=en-US&:display_count=n&:origin=viz_share_link   ). The appealing visualizations are provided below:

#### 1. Proportion of Calories per Distance by Day:
The analysis of the proportion of calories per distance by day reveals interesting insights into users activity level. Specifically, it is observed that Sundays exhibit a relatively high proportion of calories burned per distance compared to other days of the week. 

![image](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/839c537a-a16a-49b2-812e-38a3f641e2de)


#### 2. Average Steps per Hour 
The visualization showcasing the average steps taken per hour reveals interesting patterns in users activity throughout the day. It is evident that the highest average number of steps is recorded during the 6 p.m. hour. This finding suggests that users are more active and tend to engage in higher levels of physical activity during evening time.

![image](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/60435592-a0c6-472a-843e-e00f97df07d2)


#### 3. Total Steps & Total Distance by ID
This key finding highlights the relationship between total steps and total distance covered by individual users. The analysis reveals that user ID '8877689391' recorded the highest number of steps, totaling 497,241, and covered a distance of 409.4 units. This indicates that this particular user has been highly active, taking a significant number of steps and covering a considerable distance.

![image](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/9d93a9ca-36e6-4601-85aa-25c82ea75e1c)


#### 4. Maximum Sleep Duration (in hours) by Day

The sleep duaration was categorized in days, and it is identified that maximum sleep duraton is found to be 13 'hours' on 'Monday'. This finding suggests that users tend to have longer sleep periods on Mondays compared to other days of the week.

![image](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/6c6d1086-06ac-453f-aa41-4e225caaa11e)


#### 5. Correlation of Steps with Active Minutes (Very Active and Sendetary Minutes)

The analysis reveals a clear correlation between total steps, very active minutes, and sedentary minutes. As the total steps increase, the very active minutes also tend to increase, while the sedentary minutes decrease. This suggests that individuals who take more steps engage in more intense physical activity and spend less time in a sedentary state. These findings align with the recommendations of the Centers for Disease Control and Prevention (CDC), which suggests engaging in at least 30 minutes of moderate physical activity every day for optimal health. However, the data indicates that the majority of users in the dataset spend a considerable amount of time in a sedentary state, with relatively low levels of very active minutes.

![image](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/9baf23d0-9046-4e9f-b858-a39d8c6a0d4e)


#### 6. Correlation of Sleep with Each Active Minutes by day

The analysis of sleep and activity minutes over the week reveals that, on average, users spent approximately 6.98 hours sleeping, 13.31 hours in a sedentary state, 3.33 hours in light activity, 0.27 hours in fairly active moments, and 0.40 hours in very active periods.This highlights that users tend to spend a significant amount of time in sedentary behavior during the weekdays. Additionally, the data indicates that users allocates maximum time for sleep and have minimal engagement in activities.

![image](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/fe0c8aa9-ac2d-4caa-ac69-c644549c337d)


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

![dashboard](https://github.com/Tayyaba-Abro/Google-Case-Study---Bellabeat-Smart-Device-Usage/assets/47588244/b5100d79-5d16-433f-97ee-fbd33caab532)
