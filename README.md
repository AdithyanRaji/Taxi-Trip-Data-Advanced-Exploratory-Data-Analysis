# Taxi Trip Data — Exploratory Data Analysis (EDA)

An end-to-end Exploratory Data Analysis project focused on understanding taxi trip patterns, fare behaviour, temporal trends, geographic distribution, data quality, and statistical relationships using Python.

## Project Overview

This project explores a large taxi trip dataset containing approximately **3.72 million records**. The objective is to uncover meaningful patterns in trip characteristics, identify data quality issues, investigate unusual observations, and communicate findings through statistical analysis and visualizations.

The project follows a structured EDA workflow, progressing from dataset understanding and data quality assessment to advanced analysis, feature engineering, and final storytelling.

## Objectives

- Understand the structure and characteristics of the dataset.
- Identify missing values, invalid records, and unusual observations.
- Explore trip distance, duration, fare, and payment patterns.
- Investigate temporal and geographic trends.
- Examine relationships between trip characteristics and fare-related variables.
- Apply statistical techniques to test selected hypotheses.
- Engineer useful features to support deeper analysis.
- Present findings with clear interpretations and documented limitations.

## Tools & Technologies

- **Python**
- **Pandas** — data manipulation and analysis
- **NumPy** — numerical operations and feature engineering
- **Matplotlib & Seaborn** — data visualization
- **SciPy** — statistical testing
- **Jupyter Notebook** — analysis and documentation

## Project Workflow

| Stage | Analysis |
|---|---|
| 1. Dataset Understanding | Examined dataset structure, columns, data types, and summary statistics |
| 2. Data Quality Assessment | Investigated missing values, duplicates, invalid values, and inconsistencies |
| 3. Univariate & Bivariate EDA | Explored individual variable distributions and relationships |
| 4. Financial Analysis | Analysed fare amounts, totals, and fare-related components |
| 5. Temporal Analysis | Examined trip patterns across hours, days, and time periods |
| 6. Geospatial Analysis | Explored pickup and drop-off location patterns |
| 7. Aggregation & Behavioural Analysis | Compared trip behaviour across relevant groups |
| 8. Anomaly Investigation | Identified extreme distances, durations, speeds, and suspicious records |
| 9. Statistical EDA | Applied hypothesis testing and interpreted statistical significance and effect size |
| 10. Feature Engineering | Created derived variables and diagnostic flags |
| 11. Final Storytelling | Consolidated findings, limitations, and recommendations |

## Feature Engineering

Several features were created to support deeper analysis:

| Feature | Description |
|---|---|
| `trip_duration_minutes` | Trip duration calculated in minutes |
| `average_speed_mph` | Average trip speed in miles per hour |
| `fare_per_mile` | Fare amount per mile |
| `fare_per_minute` | Fare amount per minute |
| `total_per_minute` | Total trip amount per minute |
| `total_per_mile` | Total trip amount per mile |
| `pickup_period` | Pickup time grouped into broader periods |
| `is_weekend` | Indicates whether a trip occurred on a weekend |
| `distance_category` | Groups trips into Short, Medium, Long, and Very Long categories |
| `extreme_distance_flag` | Identifies trips with unusually extreme distances |
| `long_duration_flag` | Identifies unusually long-duration trips |
| `very_short_duration_flag` | Identifies trips lasting less than one minute |
| `suspicious_efficiency_flag` | Diagnostic flag for trips with a very short duration, short distance, and high fare |

These features were used for analysis and diagnosis. Flagged observations were not automatically treated as invalid or removed from the original dataset.

## Key Findings

### Trip Distance

- Short trips (under 2 miles) represented approximately **53.8%** of the dataset.
- Short and medium trips together accounted for approximately **81.3%** of records.
- Trip distance was right-skewed, with extreme observations substantially affecting the mean.

### Temporal & Behavioural Patterns

- The distribution of trip distances varied across pickup periods.
- In the filtered behavioural dataset, night trips had a lower proportion of short trips and a higher proportion of medium and long trips compared with other periods.
- These patterns represent observed associations and do not establish causation.

### Fare Analysis

- Weekday trips had a higher average fare than weekend trips in the analysed data.
- The mean difference was approximately **$1.33**.
- Although statistically significant, the standardized effect size was small (**Cohen's d ≈ 0.074**).

### Payment Type

- Payment type and weekend status showed a statistically significant association.
- The association was small (**Cramér's V ≈ 0.073**), demonstrating why statistical significance should be interpreted alongside effect size.

### Data Quality & Anomalies

- The dataset contained missing values and records with zero or unusually short durations.
- Extreme distance observations produced unrealistic calculated speeds and could distort summary statistics.
- Derived rate features were sensitive to very small denominators.
- Diagnostic flags and filtered analysis dataframes helped investigate these observations while preserving the original data.

## Statistical Methods

The project included:

- Descriptive statistics
- Distribution and percentile analysis
- Grouped aggregation
- Correlation analysis
- Welch's independent-samples t-test
- Mann–Whitney U test
- Chi-square test of independence
- Confidence intervals
- Cohen's d
- Cramér's V

The analysis considered both statistical significance and practical magnitude.

## Repository Structure

```text
Taxi-Trip-EDA/
│
├── 01_dataset_understanding.ipynb
├── 02_data_quality_assessment.ipynb
├── 03.ipynb
│
├── README.md
└── data/
    └── (Dataset files, if included)
```

*Update the filenames above if your repository uses a different structure.*

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/AdithyanRaji/Taxi-Trip-Data-Advanced-Exploratory-Data-Analysis.git
   ```

2. Navigate to the project directory:

   ```bash
   cd Taxi-Trip-EDA
   ```

3. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn scipy jupyter
   ```

4. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open the notebooks and execute the cells in sequence.

> **Note:** Update the dataset path in the notebooks according to where you store the data. The dataset is not included in this repository unless explicitly added.

## Limitations

- The analysis is based on the available dataset and may not represent all taxi trips or time periods.
- Some analyses use filtered subsets; their findings should not automatically be generalized to the full dataset.
- Extreme values and missing data can influence statistical summaries.
- Statistical associations do not establish causal relationships.
- Suspicious records require validation against the original source before being classified as errors.

## Future Improvements

- Develop an interactive dashboard for exploring trip patterns.
- Perform deeper geographic analysis of pickup and drop-off zones.
- Investigate the contribution of individual fare components to total trip amounts.
- Explore predictive modelling for trip duration or fare.
- Compare patterns across additional time periods or datasets.

## Conclusion

This project demonstrates a complete EDA workflow—from understanding and validating raw data to investigating patterns, engineering features, applying statistical tests, and communicating findings.

It highlights the importance of combining visual exploration, statistical reasoning, and data quality assessment to produce reliable and interpretable insights.

---

**Project Type:** Exploratory Data Analysis  
**Domain:** Transportation & Data Analytics  
**Status:** Completed
