
# IS 477 - Project Plan

**Project Title:** Weather Extremes and Flight Delays at Major U.S. Airports

## 1. Overview

The objective of this project is to understand how different weather conditions affect flight delays and cancellations at major U.S. airports. Severe weather, such as snow, heavy rain, and strong winds, can cause flight disruptions. However, some airports may be affected more than others depending on their location, weather patterns, and size. Our project will explore these differences by combining data from multiple sources.

We plan to study approximately ten major U.S. airports, including Chicago O'Hare, JFK, Los Angeles International, and Denver International, using data from 2024. We will use flight data from the Bureau of Transportation Statistics (BTS), weather data from the National Oceanic and Atmospheric Administration (NOAA), and airport information from the Federal Aviation Administration (FAA).

The main focus of our project will be collecting, cleaning, and combining data rather than building complex models. Using Python and Pandas, we will check the datasets for missing information, errors, and differences in formatting. We will then clean the data and combine the datasets using airport codes and dates.

Once the data is combined, we will compare flight delays under different weather conditions and create charts to show how delays vary across airports.

Throughout the project, we will follow the main steps of the data lifecycle, including collecting, checking, cleaning, combining, analyzing, and documenting data. Our goal is to create a clear and repeatable process that shows how information from different government sources can be used to better understand the relationship between weather and flight delays.

## 2. Team

Our project will be completed by four team members. Responsibilities will be divided evenly so that each member contributes to data collection, cleaning, integration, analysis, and documentation. Each member will have a primary responsibility while also working together on the overall project.

| Team Member | Primary Responsibilities |
|---|---|
| **Suha Khan** | Collect and clean BTS flight data, identify missing or incorrect values, and prepare flight records for integration. |
| **Chris Geier** | Collect and clean NOAA weather data, standardize weather measurements and dates, and prepare weather records for integration. |
| **Stephanie Li** | Collect and clean FAA airport data, standardize airport identifiers, and prepare airport information for integration. |
| **Roqaya Elmenshawy** | Develop the data integration process, combine the three cleaned datasets, and check that the datasets are joined correctly. |

All team members will contribute to the project plan, status report, final README, and GitHub repository. Individual contributions will be documented through Git commits.

## 3. Research Questions

**Primary Research Question:**

How are extreme weather conditions associated with flight delays and cancellations at major U.S. airports?

**Supporting Research Questions:**

1. Which weather conditions, including snowfall, heavy rain, and high winds, are associated with the greatest average departure delays?
2. Which airports experience the largest increases in delays during severe weather compared with normal weather conditions?
3. How do airport characteristics, such as passenger volume and hub classification, relate to differences in weather-related flight disruptions?

We will measure average departure delay minutes, percentage of flights delayed, and cancellation rates. Weather conditions will be categorized using documented thresholds. We will compare outcomes across airports and weather categories while recognizing that observed relationships do not necessarily establish causation.

## 4. Data

## 4. Datasets

### [Air Carrier Statistics (Form 41 Traffic) - U.S. Carriers](https://www.transtats.bts.gov/Tables.asp?QO_VQ=EED&QO_anzr&QO_fu146_anzr)

- **Source:** Bureau of Transportation Statistics (BTS)
- **Description:** Contains air carrier traffic and operational data for U.S. airlines. Relevant variables include airport identifiers, passenger activity, and flight-related traffic measures.
- **Role in our project:** This dataset provides the flight and airport activity information needed to study how delays and disruptions differ across major U.S. airports.
- **Join attributes:** Airport IATA code, such as ORD, JFK, DEN, and LAX
- **Constraints:** Cargo-only carrier records will be filtered out so that the project remains focused on passenger operations.

### [Local Climatological Data](https://www.ncei.noaa.gov/products/land-based-station/local-climatological-data)

- **Source:** National Oceanic and Atmospheric Administration (NOAA)
- **Description:** Provides daily and hourly surface weather observations from weather stations, including many located at or near U.S. airports. Variables include precipitation, snowfall, wind speed, temperature, and other weather conditions.
- **Role in our project:** This dataset provides the weather information needed to classify airport days based on conditions such as snow, heavy rain, and high winds.
- **Join attributes:** Weather station or airport location and observation date
- **Constraints:** We will need to make sure each airport is matched to the correct NOAA weather station and that weather observations are available for the dates included in the flight data.

### [FAA Airport Master Records](https://www.faa.gov/forms/index.cfm/go/document.information/documentID/185474)

- **Source:** Federal Aviation Administration (FAA)
- **Description:** Provides structural, administrative, and operational information for U.S. public-use airports. Variables include airport identifiers, location information, airport characteristics, and physical layout information such as runway configuration.
- **Role in our project:** This dataset gives us additional context about the airports themselves, which can help us compare whether factors such as airport size, hub status, or runway configuration are related to differences in weather-related flight disruptions.
- **Join attributes:** Airport IATA or FAA code
- **Constraints:** Some airport identifiers may need to be standardized before this dataset can be combined with the BTS and NOAA data.

## 5. Timeline

The project will be completed in stages so that each dataset is collected, assessed, cleaned, and prepared before integration. Team members will primarily own the dataset or integration tasks assigned to them, while all members will contribute to documentation, quality assessment, and final project review.

| Time Period | Task | Description | Primary Responsibility |
|---|---|---|---|
| October 12–18 | Finalize datasets and acquisition methods | Confirm the exact BTS, NOAA, and FAA datasets, source URLs, file formats, licensing information, and acquisition methods. | Suha, Chris, Roqaya |
| October 19–25 | Acquire raw datasets | Download or programmatically acquire the flight, weather, and airport datasets and organize raw files using consistent naming and folder conventions. | Suha, Chris, Roqaya |
| October 26–November 1 | Pre-integration data quality assessment | Evaluate each dataset for accuracy, completeness, timeliness, and consistency. Identify missing values, duplicate records, inconsistent identifiers, and formatting differences that may affect integration. | All team members |
| November 2–8 | Clean and standardize datasets | Apply reproducible cleaning procedures to each dataset, including standardizing dates, airport identifiers, missing-value conventions, and relevant measurement formats. | Suha, Chris, Roqaya |
| November 9–15 | Prepare datasets for integration | Confirm the selected airport records, verify NOAA weather-station mappings, standardize airport identifiers across sources, and ensure each cleaned dataset has the fields needed for integration. | Suha, Chris, Roqaya |
| November 16–19 | Initial data integration and status report | Combine the cleaned datasets using appropriate airport and date identifiers. Document join logic, unmatched records, and preliminary integration results for the Milestone 3 status report. | Stephanie, with support from all team members |
| November 20–24 | Post-integration data quality assessment | Assess the integrated dataset for accuracy, completeness, timeliness, and consistency. Evaluate join success rates, duplicate matches, unmatched records, and whether the integrated data is logically valid. | Stephanie and all team members |
| November 25–29 | Analysis and visualization | Define weather categories using documented thresholds and compare departure delays, delayed-flight percentages, and cancellation rates across airports and weather conditions. Create required visualizations. | All team members |
| November 30–December 2 | Workflow automation and reproducibility | Organize project code into separate single-purpose scripts for acquisition, cleaning, quality assessment, integration, and analysis. Connect the scripts using a run-all script or Snakemake workflow. | All team members |
| December 3–4 | Metadata and documentation | Create a data dictionary or codebook, machine-readable metadata, software dependency documentation, and descriptions of the project workflow and data sources. | All team members |
| December 5–6 | Final testing and report completion | Test the workflow from a fresh copy of the repository, fix reproducibility issues, finalize the README, and verify that all required files and documentation are included. | All team members |
| December 7 | Final project release and submission | Create the final GitHub release and submit the release URL through Canvas. | All team members |

This timeline may evolve as we learn more about the structure and quality of the selected datasets. Any changes to tasks, responsibilities, or deadlines will be documented in the status report.

## 6. Constraints

There are a few limitations and challenges we may run into throughout the project.

**Different airport identifiers:** The three datasets may not all use the same way of identifying airports. BTS may use three-letter airport codes, while NOAA may use weather-station IDs and FAA data may use its own identifiers. Because of this, we may need to create a mapping between the different identifiers before combining the datasets.

**Matching airports to weather stations:** NOAA weather data is tied to weather stations rather than directly to airports. We will need to make sure each airport is matched with the correct nearby weather station. If a station is too far from the airport or does not accurately represent the local weather, it could affect our results.

**Different levels of time detail:** The datasets may also use different time scales. Flight data may be recorded for individual flights, weather data may be hourly or daily, and FAA airport information may be annual. We may need to combine or summarize some of the data so that everything can be compared at the same level, such as by airport and day.

**Missing or inconsistent data:** We may run into missing weather values, incomplete delay information, duplicate rows, or inconsistent date and value formats. We will identify these issues during our data quality checks and document how we handle them during cleaning.

**Defining extreme weather:** We will need to decide what counts as heavy rain, high winds, or significant snowfall. The thresholds we choose could affect the results, so we plan to use established weather definitions when possible and clearly explain the thresholds we use.

**Dataset size:** BTS flight data can be very large. To keep the project manageable, we plan to focus on about ten major U.S. airports and use data from 2024. This should still give us enough variation in both weather and airport characteristics without making the project too large to process.

**Different levels of weather exposure:** Not every airport experiences the same types of extreme weather. Some airports may have many snow events, while others may have very few or none. Because of this, some comparisons may be based on fewer observations and will need to be interpreted carefully.

**Other causes of flight delays:** Weather is not the only reason flights are delayed or canceled. Airline operations, airport congestion, maintenance issues, air traffic restrictions, and delays from other airports can also play a role. Because we will not be able to control for every possible factor, we will focus on identifying relationships between weather and delays rather than claiming that weather directly caused them.

**Legal and data-use restrictions:** We plan to use government data from BTS, NOAA, and FAA. We will review and document the source, licensing, and terms of use for each dataset. If any files are too large to upload to GitHub or cannot be redistributed, we will document another reproducible way to access them.

**Reproducibility:**  Government websites and dataset formats can change over time. To make the project as reproducible as possible, we will keep track of the exact datasets we use, document our processing steps, use relative file paths, and save raw data when allowed.


## 7. Gaps

Regarding weather thresholds, we will need to establish standard aviation thresholds and thoroughly comb through our data. Because it will also be up to us to define categories (ex. What constitutes “High Wind” vs “Normal”). We will need to research standardized aviation and other weather metrics and relative percentiles.

There may also be an issue regarding station codes, as domestically airports may host either IATA codes, NOAA/WBAN numbers, or ICAO codes. We will need to wrangle our data and ensure consistency across our datasets.

We may also be missing other delay factors, thereby entirely overlooking key confounding variables such as air traffic staffing issues or other potential situations.
