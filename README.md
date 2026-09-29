# Hospital Readmission Analysis

## Project Overview
This project analyzes hospital encounter data for patients with diabetes to identify patterns associated with **30-day hospital readmissions**. 

The analysis was completed using **Python and pandas** for data preparation and exploratory analysis, followed by **Power BI** for dashboard development, DAX measures, and interactive visualization. 

The goal was not only to calculate the overall readmission rate, but also to identify patient, clinical, and hospital-utilization characteristics associated with higher readmission rates. 

## Business Question 
What patient and hospital encounter characteristics are associated with higher **30-day hospital readmission rates**?

## Tools Used
- Power BI
- Python
- pandas
- Google Colab
- DAX

## Dataset
This project uses the **Diabetes 130-US Hospitals for Years 1999-2008** dataset from the UCI Machine Learning Repository.

The dataset contains **101,766 hospital encounters** and includes information such as:
- Patient age
- Gender
- Admission Type
- Discharge Disposition
- Length of stay
- Prior inpatient visits
- Number of diagnoses
- A1C results
- Diabetes medication changes
- Hospital readmission status

A new 30-day readmission variable was created:
- '<30' = Yes
- '>30' = No
- 'NO' = No

 > The dataset contains encounter-level data. Results describe patterns within this dataset and should not be interprested as proof that any individual factor caused readmission.

## Key Findings 
- The overall **30-day readmission rate was 11.16%**.
- **11,357 of 101,766 encounters** resulted in a readmission within 30 days.
- Patients with more **prior inpatient visits** generally showed higher 30 day readmission rates.
- Readmission rates also varied by **number of diagnoses**, suggesting that greater clinical complexity may be associated with readmission risk.
- **Emergency admissions** showed a higher readmission rate than elective admissions.
- Readmission rates varied substantially across **discharge disposition**.
- Patients whose **A1C was not measured** had the highest readmission rate among the A1C categories displayed in the dashboard.
- Encounter involving a **diabetes medication change** showed slightly higher readmission rate than encounters with no medication change.
- Patients readmitted within 30 days had an average hospital stay of approximately **4.8 days**, compared with approximately **4.3 days** for patients who were not readmitted. 

## Dashboard 
![Hospital Readmission Dashboard](hospital-readmission-dashboard.png)

## Analysis Process 
1. Loaded and reviewed the hospital encouter dataset in Python.
2. Examined data shape, missing values, data types, and duplicate encounters
3. Cleaned placeholder and missing values.
4. Converted coded hospital fields into understandable categories.
5. Created a binary 30-day readmission variable.
6. Prepared a Power BI-ready dataset.
7. Imported the cleaned data into Power BI.
8. Created DAX measures for key performance indicators.
9. Built visuals comparing readmission rates across patient and encouter characteristics.
10. Added interactive slicers for gender and admission type.
11. Reviewed low-volume categories and limited certain dashboard comparisons where sample sizes were extremely small.

## Dashboard Metrics 
The dashboard inlcudes: 
- **Total Hospital Encounters:** 101,766
- **30-Day Readmissions:** 11,357
- **30-Day Readmission Rate:** 11.16%
- **Average Length of Stay:** 4.4 days

Additional visuals analyze readmission patterns by:
 - Age group
 - Admission type
 - Discharge disposition
 - Prior inpatient visits
 - Number of diagnoses
 - A1C results
 - Diabetes medication change
 - Length of stay by readmission status

Interactive slicers allow users to explore results by:
  - Gender
  - Admission Type

## Analysis Decision Log 

### 1. Defined 30-Day Readmission 

**What I noticed:**
The original readmission variable contained three categories: '<30', '>30', and 'NO'.

**Decision:**
I created a simplified 30-day readmission variable where '<30' was classified as 'Yes', while '>30' and 'NO' were classified as 'No'.

**Why:**
The business question specifically focuses on whether an encounter resulted in another hospital admission within 30 days. 

### 2. Used Unique Encounter IDs

**What I noticed:**
Each hospital encounter had a unique enounter ID. 

**Decision:**
I used 'DISTINCTCOUNT' on the encounter ID when calculating total encounters and 30-day readmissions in Power BI. 

**Why:**
This ensured that the KPI calculations were based on unique hospital encounters.

### 3. Limited Very Low-Volume Admission Categories 

**What I noticed:**
The Newborn and Trauma Center categories contained only **10 and 21 encounters**, respectively. 

**Decision:**
I excluded these categories from the interactive Admission Type slicer while keeping the underlying records in the dataset. 

**Why:**
The extremely small number of encounters produced limited and potentially misleading comparisons. 

### 4. Simplified Medication Change Labels 

**What I noticed:**
Medication-change categories were displayed das 'Ch' and 'No'.

**Decision:**
I renamed them to 'Changed' and 'No Change'.

**Why:**
Clearer labels make the dashboard easier for nontechnical users to understand. 

### 5. Limited Ambigous Gender Categories

**What I noticed:**
The dataset contained an unknown gender category. 

**Decision:**
I focused the Gender slicer to Female and Male. 

**Why**
This avoided presenting an ambigous category in the interactive comparison.

## Skills Demonstrated 
- Healthcare data analysis
- Data cleaning and validation
- Python and pandas
- Exploratory data analysis
- Power BI dashboard development
- DAX measure
- KPI development
- Data visualization
- Interactive dashboard design
- Analytical decision-making
- Business insight communcation

## Conclusion 
Among **101,766 hospital encounters**, **11,357 encounters resulted in readmission within 30 days**, producing an overall 30-day readmission rate of **11.16%**.

The analysis identified several characteristics associated with differences in readmission rates. Higher prior inpatient utilization and a greater number of diagnoses were associated with higher readmission rates, while admission type, discharge disposition, A1C category, medication-change status, and length of stay also showed meaningful variation. 

Patients who were readmitted within 30 days had a longer average hospital stay than those who were not readmitted. 

Overall, the dashboard demostrates how hospital encounter data can be used to identify patient groups and utilization patterns that may warrant closer follow-up after discharge.

These findings represent **associations within the dataset and do not establish causation**. 


## Portfolio Note
This repository is a public portfolio showcase. Full working files and development materials are maintained separately.
