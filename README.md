# Data Job Market ROI

## Questions
1. Which skills appear most often by role?


## Data Quality Assesment

The dataset contains ~785k job postings across 17 columns related to job metadata, skills, location, remote work, and compensation. Initial inspection showed that most core fields had very high completeness, particularly job_title_short, job_posted_date, job_work_from_home, company_name, and geographic columns.

A missing value audit revealed that salary-related columns had extremely low coverage (salary_year_avg 97.2% missing, salary_hour_avg 98.64% missing). Salary disclosure rates were consistently low across job roles and countries, making compensation analysis prone to selection bias. Because of this, the project focus shifted away from salary prediction and toward labor market trends, skill demand, and remote work analysis.

Skill-related fields remained highly usable, with only ~14.9% missing values in job_skills and job_type_skills. Duplicate analysis using company, title, and location showed a low duplicate rate (~0.2%), suggesting reposted jobs would have minimal impact on overall trends.

The dataset spans the full 2023 calendar year and is primarily concentrated in three major roles: Data Analyst, Data Engineer, and Data Scientist, which became the main focus of subsequent analyses.



