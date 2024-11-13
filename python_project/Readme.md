# Project Overview 

 This case study will analyse a dataset of data-related job listings from 2023 to answer the following questions:

- What were the most in-demand data-related job types in New Zealand and Australia for 2023?
- What were the most sought-after skills for data-related jobs in New Zealand and Australia in 2023?
- Were there any trends in the popularity of the sought-after skills during the course of the year 2023?


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
Using the Matplotlib and Seaborn packages to plot a summary of the advertised jobs: 

```python
sns.set_theme(style = 'ticks')
sns.barplot(data=job_title_counts, x='count', y='job_title_short', hue = 'count', legend = False)
sns.despine()  
plt.xlabel("Count")
plt.ylabel("Job Title")
plt.title("Number of Advertised Jobs")
plt.show()
```

![Job Count Chart](python_project\Images\job_type_count.png)


