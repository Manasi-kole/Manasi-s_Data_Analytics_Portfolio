# 🚴 Case_Study1_Cyclistic_bike_share
## Introduction
This analysis was completed as part of the **Google Data Analytics Professional Certificate**. It addresses a key business question for **Cyclistic**, a fictional bike-share company.
The study follows the comprehensive data analysis process (**Ask, Prepare, Process, Analyze, Share, and Act**). All data analysis and visualization were performed using **Tableau Public** to generate actionable insights and recommendations.
## 📌 Key Findings (at a glance)
- Members make up **55.3%** of rides and casual riders **44.7%** (2021, ~4.55M cleaned rides).
- **Casual riders ride about twice as long:** about 20–27 min on average vs 11–13 min for members.
- **Casual riding is seasonal and weekend-heavy:** it peaks in July–August (when casual rides exceed member rides) and nearly disappears in winter.
- **Members ride steadily** all week and all year, which points to commuting.
- **Docked bikes are used only by casual riders.**

🔗 **[View the interactive Tableau dashboard](https://public.tableau.com/views/CasestudyCyclisticBikeShareAnalysis/Dashboard1)**

## Scenario 
As a junior data analyst, my task is to understand how casual riders and annual members use Cyclistic bikes differently. The director of marketing believes the company's future success depends on maximizing the number of annual memberships. Cyclistic executives must approve recommendations, so they must be backed up with compelling data insights and professional data visualizations.
## ASK phase
Use Cyclistic's historical bike trip data to identify trends and answer:
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?
4. Top three recommendations based on your analysis.
## Prepare phase
I used Cyclistic's historical trip data for 12 months (year 2021) to analyze and identify trends.
The data has been made available by Motivate International Inc. under this [license](https://divvybikes.com/data-license-agreement).
1. Where is your data located : The data is publicly available from Divvy (Lyft Bikes and Scooters, LLC) [here](https://divvy-tripdata.s3.amazonaws.com/index.html). I used the 12 monthly files for 2021.
2. How is the data organized : The data is organized by year, quarter, and month. I downloaded the 2021 data as provided in the Google Data Analytics course.
3. Are there issues with bias or credibility in this data? Does your data ROCCC? : The data is Reliable, Original (first-party data from Divvy/Lyft), Comprehensive (12 months, 2021), Current, and Cited. One limitation: there is no rider ID, so we cannot tell whether the same casual rider returns multiple times or link rides to individual customers.
4. How did you verify the data's integrity : I consolidated all 12 monthly files in Tableau using a union and checked that every file had the same columns.
5. Are there any problems with the data? : Some records have null values (missing station IDs and locations). These are handled in the Process phase in Tableau using filters and calculated fields.
## Process phase
I used Tableau Public for data analysis and visualization. The dataset had the following columns: ride_id, rideable_type, started_at, ended_at, start_station_name, start_station_id, end_station_name, end_station_id, start_lat, start_lng, end_lat, end_lng, member_casual.
<img width="1687" height="25" alt="image" src="https://github.com/user-attachments/assets/f4fe66f6-c7ce-4c9d-b60b-0351f386654e" />

The following preprocessing steps were performed:
1. Performed Union operation in tableau to merge all datasets of 12 months.
2. Calculating "Duration" in minutes by using (**DATEDIFF('minute',[Started At],[Ended At])**) formula in tableau.
3. A duration filter of 1 to 1440 minutes (24 hours) was applied to each sheet, since rides under 1 minute or longer than 24 hours are not realistic.
4. "ValidStationId" as a calculated field because some records had null fields in start and end station id.
   formula used NOT ISNULL([Start Station ID]) AND NOT ISNULL([End Station ID])
5. Similarly, a "ValidLatLong" calculated field was created, since location should not be missing.
6. COUNT([Ride Id]) as "RideIDcount", Start_DAY: DATENAME('weekday',[Started At]) , Start_Month: DATENAME('month',[Started At]) ,End_Day, End_Month.

## Analyse
I created the charts below as part of a comparative analysis between casual and member riders:
* Count of casual riders vs members
* Bike type used by each rider group
* Time based analysis:
  * Monthly trip frequency
  * Weekly trip frequency along with average ride duration

## Share
The visualizations I created are published on my Tableau Public profile. You can view the interactive dashboard [here](https://public.tableau.com/views/CasestudyCyclisticBikeShareAnalysis/Dashboard1).

Before diving into the visualizations, note the colours used throughout the charts:



<img width="217" height="80" alt="image" src="https://github.com/user-attachments/assets/52b51758-54f2-4709-9018-322df2016fad" />

* **Member vs Casual riders ratio:** After preprocessing, casual riders make up a slightly lower share of total rides (44.7%) than annual members (55.3%).

<img width="741" height="462" alt="image" src="https://github.com/user-attachments/assets/1dee2c34-8a5c-45a9-80b3-5dae166ce765" />

- **Rider bike type distribution:** Classic bikes are the most used by both categories (members: 1,962,508 rides; casual: 1,254,365 rides). Electric bikes come second. **Docked bikes are used only by casual riders (309,652 rides)**, and members do not use them at all.

<img width="1066" height="662" alt="image" src="https://github.com/user-attachments/assets/76f45515-45ad-4284-898a-d4c21f88e118" />

**Time based analysis:**

**Monthly trip frequency:** Both rider types use Cyclistic bikes most from April to October, with the highest counts in July and August.

<img width="1066" height="660" alt="image" src="https://github.com/user-attachments/assets/204ee72f-d9fb-4a53-bceb-9d9f54b86012" />

Casual riders are much more seasonal than members: in July and August casual rides are higher than member rides, but from December to February casual riding drops to very low numbers while members keep riding.

**Weekly trip frequency with average duration** (screenshot shows January; use the Month filter on Tableau to view other months): Casual riders ride for a longer average duration than members. Members ride about 10–15 minutes on average, at a steady length every day. Casual riders ride about 20–35 minutes, and their rides are longest on Saturdays and Sundays.

<img width="1333" height="666" alt="image" src="https://github.com/user-attachments/assets/e985e72b-d88b-4975-a3dd-6d40f86d3d35" />

## Summary

**1. How do annual members and casual riders use Cyclistic bikes differently?**
- Members take short, consistent rides (about 11–13 min) every day of the week and all year round, which matches commuting to work or college.
- Casual riders take longer rides (about 20–35 min), mostly on weekends and in summer (May–September), which matches leisure and tourism use.
- Only casual riders use docked bikes.

**2. Why would casual riders buy annual memberships?**
Casual riders already ride long distances and ride often in summer. For a frequent rider, many pay-per-ride trips add up to more than a membership costs. If they see the savings and the convenience, a membership becomes the better deal.

**3. How can Cyclistic use digital media to influence casual riders to become members?**
By targeting casual riders on social media and in the app during their peak riding times (summer weekends), with messages about savings and offers built around leisure riding.

## Act: Top 3 Recommendations

1. **Launch a summer membership campaign (April–August):** Run digital ads and in-app offers just before and during the peak season, when casual riders are most active.
2. **Introduce a weekend or seasonal membership:** Casual riders ride mainly on weekends and in summer, so a cheaper weekend or summer plan can be a stepping stone to the annual membership.
3. **Show the savings on long rides:** Since casual riders ride about twice as long as members, show them in the app and on social media how much they would save with a membership, for example "You spent ₹X this month; a membership would cost ₹Y."
  




 

