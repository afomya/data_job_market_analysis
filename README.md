# Data Job Market ROI

## Questions
1. Which skills appear most often by role?


## Data Quality Assesment

The dataset contains ~785k job postings across 17 columns related to job metadata, skills, location, remote work, and compensation. Initial inspection showed that most core fields had very high completeness, particularly job_title_short, job_posted_date, job_work_from_home, company_name, and geographic columns.

A missing value audit revealed that salary-related columns had extremely low coverage (salary_year_avg 97.2% missing, salary_hour_avg 98.64% missing). Salary disclosure rates were consistently low across job roles and countries, making compensation analysis prone to selection bias. Because of this, the project focus shifted away from salary prediction and toward labor market trends, skill demand, and remote work analysis.

Skill-related fields remained highly usable, with only ~14.9% missing values in job_skills and job_type_skills. Duplicate analysis using company, title, and location showed a low duplicate rate (~0.2%), suggesting reposted jobs would have minimal impact on overall trends.

The dataset spans the full 2023 calendar year and is primarily concentrated in three major roles: Data Analyst, Data Engineer, and Data Scientist, which became the main focus of subsequent analyses.


# Processing and Analysis

The job_skills column was originally stored as strings instead of actual Python lists, so the skills first had to be parsed and cleaned before analysis. After converting the values into lists, the column was exploded into a separate dataframe (skills_df) where each row represented one skill tied to a job posting. Skills were also standardized by converting them to lowercase and removing extra whitespace.

Once cleaned, overall skill frequencies were analyzed. SQL and Python were the two most common skills across the dataset, followed by cloud and data engineering tools such as AWS, Azure, Spark, and Databricks.

To better understand how technical requirements differ across careers, the analysis focused on the three largest job categories in the dataset:

1. Data Analyst
2. Data Engineer
3. Data Scientist

A heatmap was then created using normalized skill frequencies to compare the most common skills across these roles. The results showed clear differences between them:

![Skill Demand by Role](skill_demand_by_role_hm.png)

Data Analysts were more associated with Excel, Tableau, and Power BI
Data Engineers showed stronger demand for AWS, Spark, Kafka, and Airflow
Data Scientists were more closely tied to Python, R, and machine learning tools

This analysis helped highlight how different areas of the data field require different technical skill sets.


