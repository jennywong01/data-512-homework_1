# Goal of Project
The goal of this project is to construct and analyze the dataset of monthly article traffic for a select set of pages from English Wikipedia from 2015-07 to 2023-09. The purpose of the project is to develop and follow best practices for open scientific research.


# License and Sources
- This repository is under the MIT License: https://tlo.mit.edu/learn-about-intellectual-property/software-and-open-source-licensing
- The Wikimedia Foundation REST API terms of use: https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions
- The Wikimedia API endpoint: https://wikimedia.org/api/rest_v1/#/Pageviews%20data
- The reference Wikimedia REST API code is under the license: https://creativecommons.org/licenses/by/4.0/
- Reference API document: https://drive.google.com/file/d/1XjFhd3eXx704tcdfQ4Q1OQn0LWKCRNJm/view?usp=sharing
- List of articles of Academy Award-winning movies:  https://docs.google.com/spreadsheets/d/1A1h_7KAo7KXaVxdScJmIVPTvjb3IuY9oZhNV4ZHxrxw/edit?usp=sharing

# Code Files
### `data_acquisition.ipynb`
This is the code file for data acquisition. This file produces all the data files in JSON style.

### `data_analysis.ipynb`
This is the code file for data visualization. This file produces all the graphs for data analysis.

# Data Files
### `academy_monthly_desktop_201507-202309.json`
This is a final output file from the file `data_acquisition.ipynb`, containing the monthly desktop page traffic for the subset of pages through desktop access. The JSON file follows a nested structure, with the article title as the key, and monthly information as the value.

For this data file and the following 2, they have the following structure and fields:
- key: the article title
  -   project: the specific Wikimedia project. In this case, all data are from the project "en.wikipedia"
  -   article: the title of the article
  -   granularity: the frequency of the data collection. In this case, all data are in monthly manner
  -   timestamp: a timestamp that contains the year and month of the data
  -   access: the way of access. The current JSON file is the data accessed through the desktop, and the following dataset is the data accessed through mobile devices, and the third one is a cumulative one combining the desktop and mobile acess.
  -   agent: the agent of the API usage. In this case, all agent is "user"
  -   views: the number of views in this month based on the timestamp
  
### `academy_monthly_mobile_201507-202309.json`
This is a final output file from the file `data_acquisition.ipynb`, containing the monthly mobile page traffic for the subset of pages through mobile access. The JSON file follows a nested structure, with the article title as the key, and monthly information as the value.

### `academy_monthly_cumulative_201507-202309.json`
This is a final output file from the file `data_acquisition.ipynb`, containing the monthly page traffic for the subset of pages through desktop and mobile access. The JSON file follows a nested structure, with the article title as the key, and monthly information as value.

### `sample.json`
This is a test output file from the file `data_acquisition.ipynb`, containing a small subset of monthly desktop traffic. This is a file only for JSON style check and code check.


### `thank_the_academy.AUG.2023.csv.xlsx`
This is a reference Excel file containing a list of a subset of article titles used for this analysis.

# Image Files
### `img1-max_min_avg.png`
This graph is produced by `data_analysis.ipynb`, and contains the time series for the articles that have the highest average monthly page requests and the lowest average monthly page requests for desktop access and mobile access. The graph has 4 lines (max desktop, min desktop, max mobile, min mobile).

### `img2-top10_peak.png`
This graph contains a time series for the top 10 article pages by largest (peak) page views over the entire time by access type. The graph contains the top 10 for desktop and the top 10 for mobile access (20 lines).


### `img3-fewest10_month.png`
This graph shows pages that have the fewest months of available data. The graph shows the 10 articles with the fewest months of data for desktop access and the 10 articles with the fewest months of data for mobile access.

# Special Considerations
When reading through the Excel file of a list of article titles, there is 1 page that is invalid and not able to be accessed through the API, `Victor/Victoria`. Thus, for this analysis, I removed this page in the file `data_acquisition.ipynb`.
