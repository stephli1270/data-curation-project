Status Report

Changes to Our Project

Our group originally planned to study how extreme weather conditions affect flight delays and cancellations at major U.S. airports. We planned to use flight data from the Bureau of Transportation Statistics, weather data from the National Oceanic and Atmospheric Administration, and airport information from the Federal Aviation Administration.

However, after reviewing the datasets, we realized that combining them would be more difficult than expected. The datasets used different identifiers, and matching weather observations to specific airports and flight dates would be very difficult. We were concerned that these challenges would make it difficult to complete the data integration process within the project timeline.
As a result, we decided to change our project to Traffic Crash Severity and Road Conditions in Chicago. Our new project focuses on understanding how road conditions, vehicle characteristics, and driver-related factors are associated with traffic crash injuries in Chicago.

We also decided to updated our research questions. Our main research question is: How are road conditions, vehicle characteristics, and driver-related factors associated with traffic crash severity in Chicago?

We also plan to explore three supporting questions:
How do road surface, weather, and lighting conditions relate to the number and severity of injuries reported in crashes?
Are certain vehicle types or characteristics more commonly associated with crashes involving injuries?
How do driver-related factors, such as age and other available characteristics, relate to crash severity?
These questions will help guide our analysis once the three datasets have been cleaned and combined.

Datasets

We selected three datasets from the City of Chicago's Open Data Portal:
Traffic Crashes – Crashes: Contains information about crash dates, road conditions, weather, lighting, and injuries. 
Traffic Crashes – Vehicles: Contains information about the vehicles involved in each crash, including vehicle types and characteristics. 
Traffic Crashes – People: Contains information about individuals involved in crashes, including drivers, passengers, pedestrians, and reported injuries. 
These datasets are closely related and can be combined using a shared identifier, CRASH_RECORD_ID. This makes it easier to connect information about crashes, vehicles, and people involved in the same incident. 
Although our topic and datasets changed, our overall goals of data quality assessment, cleaning, analysis, and reproducibility remain the same.

Current Progress

Our group has successfully found all three datasets for our new project and have downloaded records for 2025-2026. We have also completed an initial data quality assessment of each dataset, focusing on accuracy, completeness, timeliness, and consistency.
We examined missing values, duplicate records, data types and inconsistent formatting in our data. We also reviewed important variables such as crash dates, vehicle years, injury classifications, and crash identifiers. Through this assessment, we were able to identify issues that needed to be addressed before integration and improved our overall understanding of the datasets’ structures.
To clean the datasets, we used Python and Pandas. 
For the crashes dataset, we standardized column names and categorical values, checked crash identifiers and dates, examined numeric values, and addressed invalid coordinate information.
For the Vehicles dataset, we standardized formatting, checked vehicle identifiers and vehicle years for invalid or unrealistic values. Invalid and placeholder values were handled as missing data in such cases.
For the People dataset, we checked person identifiers and injury classifications, standardized city names, and examined missing demographic information and zip code formatting.
After cleaning, each dataset was saved as separate CSV files, allowing us to review cleaned datasets before integration.

Project Artifacts

The following files document the work completed so far:
- [Updated Project Plan](ProjectPlan.md)
- [Crashes Data Cleaning Script](REPLACE_WITH_ACTUAL_PATH)
- [Vehicles Data Cleaning Script](REPLACE_WITH_ACTUAL_PATH)
- [People Data Cleaning Script](REPLACE_WITH_ACTUAL_PATH)
- [Cleaned Crashes Dataset](REPLACE_WITH_ACTUAL_PATH)
- [Cleaned Vehicles Dataset](REPLACE_WITH_ACTUAL_PATH)
- [Cleaned People Dataset](REPLACE_WITH_ACTUAL_PATH)

These files document our progress and will be used
during the integration stage.

Next Steps

Now that we have cleaned our dataset, we must work on data integration. Per our original project plan, we intend on using the next two weeks to complete this task. We’ve laid out our plans for integration in more granularity here–
As mentioned previously, we’ve identified CRASH_RECORD_ID as the common identifier across all three datasets. Our plan is to use the Crashes dataset as the main dataset as it contains one record per crash. The Vehicles and People dataset may contain multiple records of the same crash, so directly merging all three datasets has the risk of creating duplicate crash records.
Thus, we plan to group the Vehicles dataset by CRASH_RECORD_ID and summarize various factors (ex. number/types of vehicles involved). The People dataset will also be grouped to summarize information about individuals involved and their reported injuries.
From there, we will use Pandas to perform left joins with the Crashes dataset, which should allow us to preserve the original crash records while adding information from the other datasets.
Following integration, we will check row counts, duplicate identifiers, unmatched records, and missing values to confirm that the datasets were combined correctly, and we will conduct a post-integration quality assessment to confirm that the joins worked correctly.
Regarding analysis after we have our combined dataset, we will examine relationships between crash injuries and road conditions, weather, lighting, vehicle, and driver information. We will create visualizations to communicate the patterns identified. All this information regarding our processing steps and data cleaning will be documented and organized.

Updated Timeline

Since changing topics, we have adjusted our original tasks to reflect our new datasets while keeping the overall project schedule.
Time Period

Task

Status

Oct. 12–25

Original dataset research and acquisition

Completed

Oct. 26–Nov. 8

Review original datasets and reconsider project scope

Completed

Nov. 9–15

Select new prompt datasets, assess quality, and clean data

Completed

Nov. 16–19

Develop and test data integration process

Not started

Nov. 20–24

Post-integration data quality assessment

Not started

Nov. 25–29

Crash severity analysis and visualizations

Not started

Nov. 30–Dec. 2

Workflow automation and reproducibility

Not started

Dec. 3–4

Metadata and documentation

Not started

Dec. 5–6

Final testing and report completion

Not started

Dec. 7

Final project release and submission

Not started



Challenges and Solutions

Our biggest and most evident challenge thus far has been changing our project topic after realizing that our original datasets would be too difficult to integrate. This required meeting up one again as a team to search for new datasets, review their structures, and reorient our project plan. However, we feel much more confident having selected datasets that seem more manageable to work with.

Another challenge we’ve faced has been dealing with missing and inconsistent data. Whilst cleaning, our team found that we’ve each encountered issues with categorical values, identifiers, dates, and other fields. These issues were addressed with standardizing formatting, checking for invalid values, and handling missing information where appropriate.

We also anticipate challenges during integration because the datasets contain different numbers of records for each crash, as a single incident can involve multiplev vehicles and people. From here on out, we must move with caution when summarizing records, and we intend on reviewing the combined datasets carefully to avoid incorrectly increasing the number of crashes.


Each team member has to write a short summary of their contributions to the current
milestone. Each team member should add and commit their contribution summary
themselves to the shared github repo


Stephanie: I helped with discussion on our new topic, cleaned the crashes dataset, and drafted the updates and challenges portions of this status update.


Suha: I found the new datasets for our new topic. I also cleaned the 3 datasets that we are going to be working with.

Roqaya: I contributed to our team's discussions about changing the project topic and reviewing the new datasets. I also helped update our project timeline and identify the remaining steps needed to complete the data integration, quality assessment, and final project requirements.

Chris: Helped pick a topic for our new project. Helped contribute to status report.

