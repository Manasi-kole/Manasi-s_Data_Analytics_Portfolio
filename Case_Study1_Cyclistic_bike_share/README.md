# 🚴 Case_Study1_Cyclistic_bike_share
## Introduction
This analysis was completed as part of the **Google Data Analytics Professional Certificate**. It addresses a key business question for **Cyclistic**, a fictional bike-share company.
The study follows the comprehensive data analysis process (**Ask, Prepare, Process, Analyze, Share, and Act**). All data analysis and visualization were performed using **Tableau Public** to generate actionable insights and recommendations.
## Scenario 
As a junior data analyst, understand and analyse how casual riders and annual members because, the director of marketing believes the company’s future success depends on (**maximizing the number of annual memberships**). Cyclistic executives must approve recommendations, so they must be backed up with compelling data insights and professional data visualizations.
## ASK phase
By using Cyclistic historical bike trip data identify trends.
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?
4. Top three recommendations based on your analysis.
## Prepare phase
Cyclistic’s historical trip data to analyze and identify trends (12 months data - year 2021). 
The data has been made available by Motivate International Inc. under this [license](https://divvybikes.com/data-license-agreement).)
1. Where is your data located : The data is publicly available on the website of Lyft Bikes and Scooters, LLC.
2. How is the data organized : The data is organized by year, quarter, and month, ranging from 10 years ago to now. i have downloaded the data from the google data analyics course for year 2021.
3. Are there issues with bias or credibility in this data? Does your data ROCCC? : The data is not biased, is consistent across 12 months and comprehensive.
4. How did you verify the data’s integrity : Consolidating Data Files in tableau by using tableau union.(all 12 months together)
5. Are there any problems with the data? : The data has some null values which is handled in next process phase in tableau by using filters and calculated fields.
## Process phase
I used tableau public for data analysis and visualization. The dataset had following features :
ride_id	rideable_type	started_at	ended_at	start_station_name	start_station_id	end_station_name	end_station_id	start_lat	start_lng	end_lat	end_lng	member_casual
<img width="1687" height="25" alt="image" src="https://github.com/user-attachments/assets/f4fe66f6-c7ce-4c9d-b60b-0351f386654e" />

Following measures were done as part of preprocessing :
1. Performed Union operation in tableau to merge all datasets of 12 months.
2. Calculating "Duration" in minutes by using (**DATEDIFF('minute',[Started At],[Ended At])**) formula in tableau.
3. Duration of 24hrs(i.e 1 to 1440 min ) was applied to each sheet as practically 24hrs duration for a rider is considered.
3. "ValidStationId" as a calculated field because some records had null fields in start and end station id.
   formula used NOT ISNULL([Start Station ID]) AND NOT ISNULL([End Station ID])
4. similarly "validlat/long" calculated field as location should not be missing.
5. COUNT([Ride Id]) as "RideIDcount", Start_DAY: DATENAME('weekday',[Started At]) , Start_Month: DATENAME('month',[Started At]) ,End_Day, End_Month.

## Analyse
I created below charts are part of comparative analysis between casual and member riders:
* Count of casual riders vs member ones.
* Which bike type is mostly used by riders.
* Time based analysis :
   * Monthly trip frequency
   * How many rides happened in a week along with the duration

## Share
The Visualizations I created are published on my tableau public profile. You can access it through [here](https://public.tableau.com/views/CasestudyCyclisticBikeShareAnalysis/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).

Before diving into the visualizations : This take a note of these colours I used throughout the charts.



<img width="217" height="80" alt="image" src="https://github.com/user-attachments/assets/52b51758-54f2-4709-9018-322df2016fad" />

* Member vs Casual riders ratio
Post-preprocessing, casual riders represent a marginally lower percentage of the total user base compared to annual members.

<img width="741" height="462" alt="image" src="https://github.com/user-attachments/assets/1dee2c34-8a5c-45a9-80b3-5dae166ce765" />

* Rider bike type distribution 
Among classic, electric and docked bike type,  Classic bike types are used in more amount by both cateogories. Docked bike have comparatively less users.

<img width="1066" height="662" alt="image" src="https://github.com/user-attachments/assets/76f45515-45ad-4284-898a-d4c21f88e118" />

* Time based Analysis :

  Monthly trip frequency : Both riders used cyclistic bikes more from April to October(parabolic graph). The highest count is observed in july and august.

  <img width="1066" height="660" alt="image" src="https://github.com/user-attachments/assets/204ee72f-d9fb-4a53-bceb-9d9f54b86012" />

Weekly trip frequency along with its duration :
Its observed that casual riders ride for more average duration that memeber ones. The duration is more on saturdays and sundays of the week. Members take ride on an average for 10-15 mins. Casual ones take ride for on an average of 20-35 mins.

<img width="1333" height="666" alt="image" src="https://github.com/user-attachments/assets/e985e72b-d88b-4975-a3dd-6d40f86d3d35" />

* Summary :
  




 

