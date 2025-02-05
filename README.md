# Aviation Risk Analysis and Business Recommendations

The analysis used the "Aviation Accident Database" and Tableau visualizations to identify low-risk aircraft and recommend safer models and practices for entering the aviation industry.


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

#### Using Python 

- Analyzed accident patterns across:

![freq_mapping](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/1.png)

![barplot_subplots](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/2.png)


**Insights:**

- **Accident Occurrence:** Most aviation accidents during the period of this dataset occurred in the United States and Europe across the world 
- **Injury Severity:** Most aviation accidents resulted in fatalities and other categories are much less common.
- **Aircraft Damage:** Most aviation accidents caused substantial damage to aircraft, a smaller proportion resulted in the aircraft being destroyed, and minor damage was rare.
- **Aircraft Category:** "Airplanes" are the most dominating category when comes to being involved in accidents according to this dataset. Other aero-vehicles such as "Helicopters" and "Gliders" are less frequent making "Ultralight" and "Powered parachutes" are negligible in numbers.
- **Amateur-Built Aircraft:** Most aviation accidents involve non-amateur-built aircraft, with amateur-built cases being a smaller subset.
- **Number of Engines:** Single-engine (1 engine) aircraft are more susceptible to accidents, while multi-engine aircraft (2/2+ engines) are less prone to accidents. Which indicates engine numbers play a pivotal role in avoiding aircraft accidents.
- **Engine Type:** "Reciprocating" engine types are the most prone to accidents while Turbojets, turboprops, and other engine types are less prone. This indicates engine types also play a pivotal role in avoiding aircraft accidents.
- **FAR (Federal Aviation Regulations) Description:** General Aviation (Part 91) accounts for the majority of accidents, reflecting private and small-scale aviation activity and other categories like agricultural aviation (Part 137) and commercial aviation (Part 121) occur less frequently.
- **Purpose of Flight:** "Personal flights" along with "Instructional flights" and "unknown purposes" are more susceptible to accidents while other purposes are less prone.
- **Weather Condition:** Most aviation accidents occur under VMC (Visual Meteorological Conditions), indicating clear weather. A smaller number of accidents happen under IMC (Instrument Meteorological Conditions), which involve poor visibility.
- **Broad Phase of Flight:** Landing is the most accident-prone phase of flight, followed by takeoff and cruise. Climb and descent are less frequent, and go-around phases are rare.

**Data distribution of the relevant columns**

![barplot_subplots_2](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/3.png)

- After cleaning the dataset and removing the irrelevant columns, I checked the distribution of the data in the relevant columns. Since all figures are very positively skewed the following columns will be updated with the 'Median' which won't change the data drastically.

![Pairplot](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/4.png)

- From the pair plot figure above, we can see the relationships between the numerical injury-related columns such as "Fatal", "Serious", "Minor", and "Uninjured". Since most values cluster near zero, indicating accidents with fewer injuries are common.

![Facet_Grid](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/5.png)

- From the facet grid figure above, we can see the distribution of Fatal injuries across Aircraft_Category and Severity. The count of fatalities varies between categories such as "Non-Fatal" and "Fatal" under different aircraft types.

![Joint_Plot](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/6.png)

- The joint plot above visualizes the relationship between Fatal and Serious injuries in aviation accidents with the data being further categorized by the weather conditions. From the figure above, we can infer,

    1. Most data points are clustered near the origin suggesting that most accidents involve fewer fatalities and serious injuries.
    2. Few points with high Fatal or Serious counts indicate outlier events with severe consequences.
    3. Different weather conditions are scattered across the plot, though VMC (good weather) appears more common as it has more points which was also shown in the earlier countplot as well.

![violin_plot](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/7.png)

- The violin plot above visualizes the distribution of Fatal injuries across different Weather conditions. From the figure above we can infer,
   
   1. Across all weather conditions, most accidents result in very few fatalities, with density highest near zero.
   2. Each condition has some extreme cases (Outliers) with high fatality counts causing the long tails in the figure.
   3. No significant difference in fatality distributions between VMC and IMC conditions.

![fatalities_by_flight_type](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/8.png)

The figure above visualizes the categories of business that have the least fatalities associated with that business type by ranking the average fatalities by flight type. From the figure above we can infer,

   1. The categories such as skydiving, firefighting, and executive flights show the highest risk of fatalities,
   2. The categories such as instructional, banner tow, and aerial application activities demonstrate the least risk.

![aircraft_count_by_damage by Purpose](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/9.png)

The heatmap above visualizes the count of aircraft damage by purpose. From the heatmap above we can infer,

   1. It seems that "Minor" damage is the most frequent across all flight purposes.
   2. "Personal" flights have the highest overall count of damage, with a significant number of "Minor" and "Substantial" damages.
   3. "Banner Tow", "Firefighting" and "Glider Tow" appear to have no minor damages.

![aircraft_count_by_damage by Purpose](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/10.png)

The heatmap above visualizes the engine count of the accidents under different categories of weather. From the heatmap above we can infer,

  1. VMC (Visual Meteorological Conditions) has the highest number of aircraft with 1 engine, followed by IMC (Instrument Meteorological Conditions). (This was also visualized earlier as well)
  2. Aircraft with 4 engines are relatively rare across all weather conditions suggesting aircraft with more engines are less prone to accidents.

#### Using Tableau

## Key Findings
1. **Manufacturer and Model Reliability**:
![Manufacturer and Model Reliability](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/T7.PNG)
   - Certain aircraft models demonstrated consistently lower accident rates relative to their market share, suggesting higher reliability.

2. **Commercial vs. Private Aviation**:
![Commercial vs. Private Aviation](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/T5.PNG)
   - Commercial aviation showed fewer accidents per flight than private aviation due to stricter regulatory oversight and maintenance standards.

3. **Weather-Related Risks**:
![Weather-Related Risks](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/T6.PNG)
   - Adverse weather conditions, such as low visibility, significantly contributed to accidents, highlighting the importance of weather-compatible aircraft.

## Risk Mitigation Recommendations
1. **Aircraft Selection**: Focus on models with a proven safety record and strong maintenance support from manufacturers.
2. **Weather Compatibility**: Prioritize aircraft with advanced navigation and weather systems to reduce risks during adverse conditions.
3. **Operational Practices**: Invest in training and compliance systems to enhance safety in private aviation operations.

## Tableau Dashboard Visualizations

The analysis also includes Tableau dashboards to provide interactive visualizations of the curated data, offering deeper insights into accident trends and risk factors. Few insights from the data i also shown in [Tableau Dashboard and Sheets](https://public.tableau.com/app/profile/md.reuzwan.hassan/viz/AviationAccidentDatabaseTableauDashboards/Dashboard1)

### **Dashboard 1**
![tableau_dashboard_1](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/D1.PNG)

### **Dashboard 2**
![tableau_dashboard_2](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/D2.PNG)

## Business Impact and making business recommendations

After Determining which manufacturer planes are good for general business use based on the damage. I highlighted the manufacturer's accident counts, damage statistics, and an overall risk score to identify low-risk planes for potential purchase and introduced a new risk metric named "Risk_Score". 
The insights and recommendations enable decision-makers to strategically evaluate aircraft purchase options strategically, ensuring a balance between operational efficiency and safety while entering the aviation market. I listed down the top 5 least risky and least safe makers to invest in shown in the tables below.

### **Least Safe**
![Least_Risky](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/11.png)

### **Least Risky**
![Least_Risky](https://raw.githubusercontent.com/RezuwanHassan262/Aviation-Accident-Data-Analysis-and-Business-Recommendations/main/images/12.png)

I reached some conclusions after the analysis which will help identify manufacturers with higher overall risk based on accident data and severity categories.

1. The analysis highlights that skydiving, firefighting, and executive flights carry the highest risk of fatalities, whereas activities like instructional flying, banner towing, and aerial applications pose the lowest risk.
2. The findings suggest that single-engine aircraft may offer better survival prospects in adverse weather conditions.
3. The extensive dataset for single-engine aircraft likely enhances the precision of the results.
