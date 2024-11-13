# Project Overview 

 This case study will analyse a dataset of data-related job listings from 2023 to answer the following questions:

- What were the most in-demand data-related job types in New Zealand and Australia for 2023?
- What were the most sought-after skills for data-related jobs in New Zealand and Australia in 2023?
- Were there any trends in the popularity of the sought-after skills during the course of the year 2023?

# Tools Used 
The following tools were used for this project: 

**- Python** -  main programming language used for the project
- Pandas Library - data manipulation, cleaning and analysis 
- Matplotlib Library - data visualisations 
- Seaborn Library - tools used to enhance the visualisations 

**- Visual Studio Code**  - Integrated development environment/ code editor

**- Jupyter Notebook** - Used to run the python scripts (via VS Code)

**- Git and Github** - Version control, sharing the code online 

# Exploratory Data Analysis (EDA)

An initial exploration of the dataset was conducted to locate areas for data cleaning and to get a better understanding the basic structure, patterns and relationships within a dataset. 

The following packages were imported for this step: 
``` python
import pandas as pd
import matplotlib.pyplot as plt 
import seaborn as sns
from datasets import load_dataset
```

## Data Structure 
Getting a overview of the data structure by running the head(), info(), and details() methods on the data. A summary of the dataset is below: 

Index: 15409 entries, 90 to 785687
Data columns (total 17 columns)
dtypes: bool(3), datetime64[ns](1), float64(2), object(11)


## Cleaning the Data
The following steps were taken to clean the data: 
- Dropping the duplicate rows. 
- Converting the 'job_post_date' column into datetime type.
- Creating a new filtered data frame with job postings from only New Zealand and Australia and assigning it to the variable 'df_anz'.
- Assigning a name to the data frame index.
- Resetting the index for 'df_anz'.

# EDA Visualisations 
### Using the Matplotlib and Seaborn packages to plot a summary of the advertised jobs: 

```python
sns.set_theme(style = 'ticks')
sns.barplot(data=job_title_counts, x='count', y='job_title_short', hue = 'count', legend = False)
sns.despine()  
plt.xlabel("Count")
plt.ylabel("Job Title")
plt.title("Number of Advertised Jobs")
plt.show()
```

![Job Count Chart](Images\job_type_count.png)


### Insights: 
- Data engineer roles were the most frequently listed in New Zealand and Australia in 2023. 
- Data analysts were more in demand in 2023 than software engineers and data scientists. 
- There was a low demand of machine learning engineers compared to other data related roles. 



### Using the Matplotlib and Seaborn packages to plot a summary of the advertised jobs:


```python
fig, ax = plt.subplots(1, 2, figsize=(12, 8))  # Set the figure size to double

column_dict = {
    'job_work_from_home': 'Work From Home?',
    'job_no_degree_mention': 'Degree Required?'
}

for i, (column, title) in enumerate(column_dict.items()):
    ax[i].pie(df_anz[column].value_counts(), startangle=90, autopct='%1.1f%%', labels=['No', 'Yes'], colors=sns.color_palette("PuBu"))
    ax[i].set_title(title)

plt.show()
```
![WFH and Degree Charts](Images\wfh_degree_pie.png)
### Insights: 
- Only 5.2% of the roles offered a work from home option on the job listing while only 48.5% required a the applicants to have a degree.   
- However, it is important to note the possible limitations of this dataset since the data was collected via web scraping. The jobs with a work from home option or a degree requirement may not have listed this online.

# Detailed Insights and Trend Analysis 
This part of the project can be found in the following Jupyter Notebook file: 


