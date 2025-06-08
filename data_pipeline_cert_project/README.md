# 1001-Experiments Data Engineering Project

## Overview

This project is part of the Data Engineer Certification practical exam and focuses on cleaning, transforming, and integrating multiple health-related datasets for **1001-Experiments** — a company that designs personalized supplements based on user health data.

The goal is to produce a comprehensive dataset that combines:
- Daily health metrics from wearable devices
- Supplement usage logs
- User demographic profiles
- Experiment metadata

The final dataset enables more accurate health analyses and tailored supplement recommendations.

---

## Datasets

The project uses the following CSV files:
- `user_health_data.csv` – Daily health metrics and activity scores
- `supplement_usage.csv` – Supplement intake logs per user
- `experiments.csv` – Supplement experiment metadata
- `user_profiles.csv` – User demographic and contact information

---

## Main Function

```python
merge_all_data(user_health_data_path, supplement_usage_path, experiments_path, user_profiles_path)
Parameters
user_health_data_path: Path to user_health_data.csv

supplement_usage_path: Path to supplement_usage.csv

experiments_path: Path to experiments.csv

user_profiles_path: Path to user_profiles.csv

Returns
A pandas.DataFrame containing the merged and cleaned dataset with the following columns:

Column Name	Description
user_id	Unique identifier for each user
date	Date of the record (health or supplement)
email	User's email address
user_age_group	Age group bucket based on user's age
experiment_name	Name of the experiment (if any)
supplement_name	Supplement name or 'No intake'
dosage_grams	Dosage in grams (converted from mg if needed)
is_placebo	Boolean: whether supplement is a placebo
average_heart_rate	Avg heart rate from wearable device
average_glucose	Avg glucose level
sleep_hours	Total sleep hours the night before
activity_level	Activity level score (0-100)

How to Run
Clone this repository:

bash
Copy
Edit
git clone https://github.com/your-username/1001-experiments-data-engineering.git
cd 1001-experiments-data-engineering
Ensure Python and the required libraries are installed:

bash
Copy
Edit
pip install pandas numpy
Place the 4 CSV files in the root folder or update the paths accordingly.

Run the script:

python
Copy
Edit
from script import merge_all_data

df = merge_all_data(
    'user_health_data.csv',
    'supplement_usage.csv',
    'experiments.csv',
    'user_profiles.csv'
)

print(df.head())
Notes
Missing supplement intake days are marked as 'No intake'.

Dosage values are normalized to grams.

Users without supplement data still appear if health data is present.

The function is robust to missing values and inconsistent formatting.

Author
Randy Funwie Tanwie
