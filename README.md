# COVID-19 Data Analysis Project (Bangladesh) 📊

This project analyzes COVID-19 pandemic data with a specific focus on **Bangladesh**. It processes monthly data to calculate critical healthcare metrics like death rates and recovery rates, helping to identify the pandemic's peak periods and overall trends.

## Features & Analysis Steps
1. **Data Filtering:** Isolates specific country data (e.g., Bangladesh) from the main dataset.
2. **Data Cleaning:** Checks for missing or null values in the filtered dataset to ensure accuracy.
3. **Feature Engineering:** Extracts the year and month (e.g., `2020-03`) from raw date columns, ignoring specific days.
4. **Data Aggregation:** Performs a `groupby` operation by month to find the maximum number of confirmed cases, deaths, and recoveries.
5. **Metric Calculation:** - **Death Rate (%)** = (Total Deaths / Total Confirmed) * 100
   - **Recovery Rate (%)** = (Total Recovered / Total Confirmed) * 100
6. **Insight Generation:** Identifies the month with the highest death rate and calculates the overall average recovery rate throughout the pandemic.

## Technologies Used 🛠️
- **Python 3**
- **Pandas** (Data Manipulation & Analysis)
- **Jupyter Notebook**

## Python Implementation 💻

```python
# Calculating the Death Rate (%) and Recovery Rate (%)
monthly_data['Death_Rate'] = (monthly_data['Deaths'] / monthly_data['Confirmed']) * 100
monthly_data['Recovery_Rate'] = (monthly_data['Recovered'] / monthly_data['Confirmed']) * 100

# Find the month with the maximum death rate
highest_death = monthly_data.loc[monthly_data['Death_Rate'].idxmax()]

# Analyze the average recovery rate across the dataset
average_recovery_rate = monthly_data['Recovery_Rate'].mean()
```

## Sample Output 📋

```text
--- 📊 Project Summary Report (Bangladesh) ---
The highest death rate was in the month of: 2020-03.
The death rate in that month was: 9.80%
The average recovery rate for Bangladesh throughout the pandemic was: 67.53%

# 4. Printing the final summary report
print(f"--- 📊 Project Summary Report (Bangladesh) ---")
print(f"The highest death rate was in the month of: {highest_death['Month']}.")
print(f"The death rate in that month was: {highest_death['Death_Rate']:.2f}%")
print(f"The average recovery rate for Bangladesh throughout the pandemic was: {average_recovery_rate:.2f}%")
