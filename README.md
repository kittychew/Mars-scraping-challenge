# Mars Weather Data Scraper and Analyzer

## Overview

This project is a web scraping application that collects and analyzes weather data from Mars using Python. The data is sourced from the Mars Temperature Data Site and includes various metrics such as minimum temperature and atmospheric pressure.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Data Scraping](#data-scraping)
- [Data Analysis](#data-analysis)
- [Results](#results)
- [License](#license)

## Installation
To set up the project on your local machine, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/kittychew/mars-weather-data.git
2.	Navigate to the project directory:
    ```bash
    cd mars-weather-data
3.	Install the required packages:
    ```bash
    pip install splinter beautifulsoup4 pandas matplotlib

  ## Usage
  To run the scraping and data analysis, execute the following script:
    ```bash
    python mars_weather.py

  ## Data Analysis 
  The analysis includes determining:
  	•	The number of Martian months.
  	•	The number of Martian days’ worth of data.
  	•	The coldest and warmest months based on average temperatures.
  	•	The atmospheric pressure variations by month.
  	•	An estimate of Earth days in a Martian year.

## Results
The results of the Mars weather data scraping and analysis include the following findings:

1. **Number of Martian Months**: 
   The analysis found that there are **12 months** on Mars, which can be verified using the following code:
   ```python
   num_months = mars_df['month'].nunique()
   print(f"Number of Martian months: {num_months}")

2. **Martian Days' Worth of Data**: 
   The dataset contains data for **1867 Martian days** (sols). This was calculated using the following code:
   ```python
   martian_days_count = mars_df['sol'].nunique()
   print(f"Number of Martian days in the dataset: {martian_days_count}")

3. **Average Low Temperature by Month**: 
   The average low temperatures for each Martian month were calculated using the following code:
   ```python
   avg_low_temp = mars_df.groupby('month')['min_temp'].mean()
   print(avg_low_temp)

    The resulting average low temperatures (in Celsius) by Martian month are as follows:
    month
      1    -77.160920
      2    -79.932584
      3    -83.307292
      4    -82.747423
      5    -79.308725
      6    -75.299320
      7    -72.281690
      8    -68.382979
      9    -69.171642
      10   -71.982143
      11   -71.985507
      12   -74.451807
  
4. **Average Pressure by Martian Month**: 
   The average atmospheric pressure for each Martian month was calculated using the following code:
   ```python
   avg_pressure = mars_df.groupby('month')['pressure'].mean()
   print(avg_pressure)

   The resulting average atmospheric pressures (in Pascals) by Martian month are as follows:
    month
      1     862.488506
      2     889.455056
      3     877.322917
      4     806.329897
      5     748.557047
      6     745.054422
      7     795.105634
      8     873.829787
      9     913.305970
      10    887.312500
      11    857.014493
      12    842.156627

5. **How Many Terrestrial Days Exist in a Martian Year**: 
   To estimate the number of terrestrial days **(675 days)** in a Martian year, we used the following code:
   ```python
   mars_df.plot(x='terrestrial_date', y='min_temp')
   plt.title('Minimum Temperature on Mars')
   plt.xlabel('Terrestrial Date')
   plt.ylabel('Minimum Temperature (°C)')
   plt.show()
  
## License 
This project is licensed under the MIT License.

## Acknowledgments
I would like to thank ChatGPT for its assistance in various aspects of this project, including code examples and guidance.
