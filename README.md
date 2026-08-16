# RTA Accident Dataset Analysis

## Project Overview

This project analyses a real-world Road Traffic Accident (RTA) dataset using Python. The objective is to identify accident patterns, understand factors associated with accident frequency and severity, and extract evidence-based insights that can support road-safety interventions.

Each row represents a road accident event with information about timing, road and environmental conditions, vehicles, drivers, casualties, and accident severity.

The project follows a practical data-analysis workflow:

**Data Inspection → Data Cleaning → EDA → Label Encoding → Feature Selection → Feature Engineering → Standardisation → Insights & Recommendations**

---

## Objectives

### Analytical Objectives

- Identify major factors associated with road accidents.
- Analyse accident frequency across different times and days.
- Compare accidents across weather, road-surface, light, and vehicle conditions.
- Understand which conditions are associated with more severe accidents.
- Analyse the relationship between vehicles involved and casualties.
- Extract meaningful patterns from the dataset.
- Develop evidence-based road-safety recommendations.

### Learning Objectives

- Apply Python and Pandas to a real-world dataset.
- Perform systematic data inspection and cleaning.
- Conduct univariate, bivariate, and multivariate EDA.
- Create meaningful visualisations.
- Extract and communicate data-driven insights.
- Apply feature selection and feature engineering.
- Use Generative AI as a coding and analytical assistant.

---

## Dataset

**File:** `RTA_Dataset.csv`

The dataset contains **12,316 accident records and 32 variables**.

Important variables include:

- `Time`
- `Day_of_week`
- `Age_band_of_driver`
- `Driving_experience`
- `Type_of_vehicle`
- `Weather_conditions`
- `Road_surface_conditions`
- `Light_conditions`
- `Road_allignment`
- `Types_of_Junction`
- `Number_of_vehicles_involved`
- `Number_of_casualties`
- `Accident_severity`

The dataset also contains additional driver, vehicle, casualty, road, and accident-related attributes.

---

## Project Workflow

```text
Import Packages
       ↓
Read & Inspect Data
       ↓
Data Cleaning
       ↓
Exploratory Data Analysis
       ↓
Label Encoding
       ↓
Feature Selection
       ↓
Feature Engineering
       ↓
Standardisation
       ↓
Key Findings & Recommendations
```

---

# 1. Import Packages

Python libraries used for data manipulation, analysis, and visualisation include:

- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

---

# 2. Data Loading & Initial Inspection

The dataset is loaded into a Pandas DataFrame and inspected before any transformation.

The inspection covers:

- Dataset dimensions
- Sample records
- Column names
- Data types
- Numerical statistics
- Categorical statistics
- Unique values
- Missing values
- Duplicate records
- Accident severity distribution
- Casualty statistics

The purpose is to understand the structure and quality of the data before cleaning.

---

# 3. Data Cleaning

Cleaning is based on actual data-quality issues identified in the dataset rather than applying unnecessary transformations.

### Missing Values

Literal `"na"` values are converted to proper Pandas missing values (`NaN`). Remaining missing values are inspected and treated according to the meaning of each variable.

Categorical missing values are not blindly replaced with the mode because doing so can distort the observed accident patterns.

### Duplicates

Exact duplicate records are checked and removed only when they are actually present.

### Data Types

The `Time` column is converted into an appropriate datetime representation so that hour and time-period analysis can be performed.

Numerical variables such as `Number_of_vehicles_involved` and `Number_of_casualties` are validated rather than unnecessarily converted when already correctly typed.

### Validation

Logical checks are performed on numerical variables to identify impossible values.

Extreme observations are not automatically removed because unusually severe accidents may represent genuine and important events.

---

# 4. Exploratory Data Analysis

EDA is the core analytical stage of the project.

## 4.1 Univariate Analysis

Individual variables are analysed to understand their distributions.

Examples:

- Accident severity
- Day of week
- Hour of accident
- Weather conditions
- Road-surface conditions
- Light conditions
- Vehicle types

## 4.2 Bivariate Analysis

Relationships between accident severity and important factors are examined.

Key relationships include:

- Weather conditions vs accident severity
- Light conditions vs accident severity
- Road-surface conditions vs accident severity
- Vehicle type vs accident severity
- Hour vs accident severity
- Day of week vs accident severity
- Driving experience vs accident severity
- Driver age band vs accident severity
- Vehicles involved vs casualties

Both counts and within-category percentages are considered.

## 4.3 Multivariate Analysis

Multiple factors are analysed together to identify more meaningful combinations, including:

- Hour + weather + severity
- Weather + road surface + severity
- Vehicle type + weather + severity

## 4.4 Key Findings & Insights

The notebook calculates evidence-based findings from the actual dataset.

The analysis focuses on:

- Peak accident hours and periods
- Highest-accident days
- Dominant weather conditions
- Important road and light conditions
- Most frequently involved vehicle types
- Overall accident severity distribution
- Severity proportions across environmental conditions
- Severity patterns across driver characteristics
- Relationship between vehicles involved and casualties
- Conditions associated with disproportionately severe accidents

A key analytical principle is distinguishing **frequency from severity**. A category with the most accidents is not necessarily the category with the highest proportion of severe accidents.

---

# 5. Label Encoding

A separate encoded version of `Accident_severity` is created while preserving the original categorical column.

The original severity column remains available for readable EDA and interpretation.

Other nominal categorical variables are not blindly label-encoded because assigning numbers to categories such as weather or vehicle type can imply an artificial order.

---

# 6. Feature Selection

Feature selection identifies variables most relevant to the project's analytical objectives.

The process considers:

- Relevance to accident frequency
- Relevance to accident severity
- Redundant information
- Variables with little or no variation
- Interpretability
- Analytical usefulness

The complete cleaned dataset is retained while a focused analytical dataset can be created for the main analysis.

---

# 7. Feature Engineering

Meaningful variables are derived from existing columns.

Examples include:

### Hour

Extracted from `Time` to analyse accident patterns throughout the day.

### Time Period

Accidents can be grouped into periods such as:

- Morning
- Afternoon
- Evening
- Night

### Weekend Indicator

A feature can be created to distinguish weekends from weekdays.

Feature engineering is limited to variables that provide meaningful analytical value.

---

# 8. Standardisation

Numerical variables can be standardised where required without overwriting the original values.

Since the current project focuses on data analysis rather than machine learning, standardisation is treated as a preprocessing step rather than a requirement for EDA.

---

# Tools & Technologies

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Generative AI

---

# Project Deliverables

### 1. Cleaned Dataset

A validated dataset with appropriate missing-value treatment, data-type handling, duplicate checks, and derived analytical features.

### 2. Key Insights

Evidence-based findings describing important accident patterns and severity-related conditions.

### 3. Visualisations

Professional charts covering:

- Accident frequency by time
- Accident frequency by day
- Severity distribution
- Severity by weather
- Severity by road conditions
- Severity by light conditions
- Vehicle involvement
- Casualty relationships

### 4. Summary & Recommendations

A concise interpretation of the major findings and potential road-safety interventions.

---

# Repository Structure

```text
RTA-Accident-Analysis/
│
├── RTA_Dataset.csv
├── Accident_Analysis.ipynb
└── README.md
```

---

# Key Analytical Principles

1. Inspect before cleaning.
2. Clean only actual data-quality problems.
3. Do not replace missing values blindly.
4. Do not remove genuine extreme observations without justification.
5. Use percentages when comparing categories with different frequencies.
6. Distinguish association from causation.
7. Preserve original information whenever possible.
8. Every visualisation should answer an analytical question.
9. Insights should be supported by evidence from the dataset.
10. Recommendations should be based on observed patterns rather than assumptions.

---

# Conclusion

This project demonstrates an end-to-end data-analysis workflow on a real-world road traffic accident dataset.

The goal is not simply to create charts, but to move from:

**Raw Data → Clean Data → Exploration → Evidence → Insights → Recommendations**

The analysis provides a foundation for understanding when, where, and under what conditions road accidents occur and which factors are associated with more severe outcomes.

---

## Author

**CH Sai Abhijith Reddy**

*Aspiring Data Scientist*
