# Aviation Risk Analysis and Recommendations

The analysis used the "Aviation Accident Database" and Tableau visualizations to identify low-risk aircraft and recommend safer models and practices for entering the aviation industry.

Business Problem Statement:


## Project Overview
This project supports a company’s strategic expansion into the aviation industry by identifying low-risk aircraft. The goal is to provide actionable insights and recommendations to minimize commercial and private aviation risks.

## Dataset
The dataset that was utilized for this project is the ["Aviation Accident Database & Synopses, up to 2023"](https://www.kaggle.com/datasets/khsamaha/aviation-accident-database-synopses) from Kaggle. The description of the dataset and a sample of the dataset is given below

**Column Names**
| Column Name               | Description                                                                 |
|---------------------------|-----------------------------------------------------------------------------|
| `Event_Id`                | Unique identifier for the aviation accident/incident.                      |
| `Investigation_Type`      | Type of investigation (e.g., Accident, Incident).                          |
| `Accident_Number`         | Official accident number assigned by the investigating authority.          |
| `Event_Date`              | Date of the aviation accident/incident.                                    |
| `Location`                | Location where the accident/incident occurred (city, state, country).      |
| `Country`                 | Country where the accident/incident occurred.                              |
| `Latitude`                | Latitude coordinate of the accident location.                              |
| `Longitude`               | Longitude coordinate of the accident location.                             |
| `Airport_Code`            | Code of the airport (if applicable).                                       |
| `Airport_Name`            | Name of the airport (if applicable).                                       |
| `Injury_Severity`         | Severity of injuries (e.g., Fatal, Serious, Minor, None).                  |
| `Aircraft_Damage`         | Extent of damage to the aircraft (e.g., Destroyed, Substantial, Minor).    |
| `Aircraft_Category`       | Category of the aircraft (e.g., Airplane, Helicopter, Glider).             |
| `Registration_Number`     | Registration number of the aircraft.                                       |
| `Make`                    | Manufacturer of the aircraft.                                              |
| `Model`                   | Model of the aircraft.                                                     |
| `Amateur_Built`           | Indicates if the aircraft was amateur-built (Yes/No).                      |
| `Number_of_Engines`       | Number of engines on the aircraft.                                         |
| `Engine_Type`             | Type of engine(s) on the aircraft (e.g., Piston, Turboprop, Turbojet).     |
| `FAR_Description`         | Federal Aviation Regulation (FAR) description related to the accident.     |
| `Schedule`                | Indicates if the flight was scheduled or non-scheduled.                    |
| `Purpose_of_Flight`       | Purpose of the flight (e.g., Personal, Training, Aerial Application).      |
| `Air_Carrier`             | Name of the air carrier (if applicable).                                   |
| `Total_Fatal_Injuries`    | Total number of fatal injuries.                                            |
| `Total_Serious_Injuries`  | Total number of serious injuries.                                          |
| `Total_Minor_Injuries`    | Total number of minor injuries.                                            |
| `Total_Uninjured`         | Total number of uninjured individuals.                                     |
| `Weather_Condition`       | Weather conditions at the time of the accident (e.g., VMC, IMC).           |
| `Broad_Phase_of_Flight`   | Phase of flight during the accident (e.g., Takeoff, Cruise).               |
| `Report_Status`           | Status of the accident report (e.g., Final, Preliminary).                  |
| `Publication_Date`        | Date the accident report was published.                                    |
| `Synopsis`                | summary or synopsis of the accident.                                       |

**Dataset Samples**

| Event.Id       | Investigation.Type   | Accident.Number   | Event.Date   | Location        | Country       | Latitude | Longitude | Airport.Code | Airport.Name | Injury.Severity   | Aircraft.damage   | Aircraft.Category | Registration.Number   | Make     | Model    | Amateur.Built   | Number.of.Engines | Engine.Type   | FAR.Description | Schedule | Purpose.of.flight   | Air.carrier | Total.Fatal.Injuries | Total.Serious.Injuries | Total.Minor.Injuries | Total.Uninjured | Weather.Condition   | Broad.phase.of.flight   | Report.Status   | Publication.Date   |
|:---------------|:---------------------|:------------------|:-------------|:----------------|:--------------|-----------:|------------:|---------------:|---------------:|:------------------|:------------------|--------------------:|:----------------------|:---------|:---------|:----------------|--------------------:|:--------------|------------------:|-----------:|:--------------------|--------------:|-----------------------:|-------------------------:|-----------------------:|------------------:|:--------------------|:------------------------|:----------------|:-------------------|
| 20001218X45444 | Accident             | SEA87LA080        | 1948-10-24   | MOOSE CREEK, ID | United States | nan      | nan      | nan | nan | Fatal(2)          | Destroyed         | nan | NC6404                | Stinson  | 108-3    | No              | 1 | Reciprocating | nan | nan | Personal            | nan | 2 | 0 | 0 | 0 | UNK                 | Cruise                  | Probable Cause  | nan                |
| 20001218X45447 | Accident             | LAX94LA336        | 1962-07-19   | BRIDGEPORT, CA  | United States | nan      | nan      | nan | nan | Fatal(4)          | Destroyed         | nan | N5069P                | Piper    | PA24-180 | No              | 1 | Reciprocating | nan | nan | Personal            | nan | 4 | 0 | 0 | 0 | UNK                 | Unknown                 | Probable Cause  | 19-09-1996         |
| 20061025X01555 | Accident             | NYC07LA005        | 1974-08-30   | Saltville, VA   | United States | 36.9222 | -81.8781 | nan | nan | Fatal(3)          | Destroyed         | nan | N5142R                | Cessna   | 172M     | No              | 1 | Reciprocating | nan | nan | Personal            | nan | 3 | nan | nan | nan | IMC                 | Cruise                  | Probable Cause  | 26-02-2007         |
| 20001218X45448 | Accident             | LAX96LA321        | 1977-06-19   | EUREKA, CA      | United States | nan      | nan      | nan | nan | Fatal(2)          | Destroyed         | nan | N1168J                | Rockwell | 112      | No              | 1 | Reciprocating | nan | nan | Personal            | nan | 2 | 0 | 0 | 0 | IMC                 | Cruise                  | Probable Cause  | 12-09-2000         |
| 20041105X01764 | Accident             | CHI79FA064        | 1979-08-02   | Canton, OH      | United States | nan      | nan      | nan | nan | Fatal(1)          | Destroyed         | nan | N15NY                 | Cessna   | 501      | No              | nan | nan           | nan | nan | Personal            | nan | 1 | 2 | nan | 0 | VMC                 | Approach                | Probable Cause  | 16-04-1980         |

## Steps Undertaken

### 1. Data Preparation
![clean data](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/13.jpg) 
- Cleaned missing and inconsistent values.
- Standardized features like aircraft type and manufacturer.
- Removed irrelevant columns to focus on critical risk factors.

### 2. Exploratory Data Analysis (EDA)
- Analyzed accident patterns across:

![freq_mapping](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/1.png)

  - **Aircraft accident occurrence frequency mapping**

![barplot_subplots](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/2.png)
  
  - **Injury severity**
  - **Aircraft damage**
  - **Aircraft category**
  - **Manufacturer**
  - **Number of engines**
  - **Engine types**
  - **FAR description**
  - **Purpose of use**
  - **Weather conditions**
  - **Phase of flight during which the accident occurred**
    
- Examined trends over time to understand how risks evolved.

## Key Findings
1. **Manufacturer and Model Reliability**:
   - Certain aircraft models demonstrated consistently lower accident rates relative to their market share, suggesting higher reliability.

2. **Commercial vs. Private Aviation**:
   - Commercial aviation showed fewer accidents per flight compared to private aviation due to stricter regulatory oversight and maintenance standards.

3. **Weather-Related Risks**:
   - Adverse weather conditions, such as low visibility, significantly contributed to accidents, highlighting the importance of weather-compatible aircraft.

## Risk Mitigation Recommendations
1. **Aircraft Selection**:
   - Focus on models with a proven safety record and strong maintenance support from manufacturers.

2. **Weather Compatibility**:
   - Prioritize aircraft with advanced navigation and weather systems to reduce risks during adverse conditions.

3. **Operational Practices**:
   - Invest in training and compliance systems to enhance safety in private aviation operations.

## Tableau Dashboard Visualizations

The analysis also includes Tableau dashboards to provide interactive visualizations of the curated data, offering deeper insights into accident trends and risk factors. Few insights from the data i also shown in [Tableau Dashboard and Sheets](https://public.tableau.com/app/profile/md.reuzwan.hassan/viz/AviationAccidentDatabaseTableauDashboards/Dashboard1)

### **Dashboard 1**
![tableau_dashboard_1](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/D1.PNG)

### **Dashboard 2**
![tableau_dashboard_2](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/D2.PNG)

## Business Impact
The insights and recommendations enable decision-makers to strategically evaluate aircraft purchase options, ensuring a balance between operational efficiency and safety while entering the aviation market.

