
# California Census Data Retrieval (Income By City By Year - census_api_california_income_by_city_2015_2021.ipynb)

## Introduction
This Python script retrieves income and population data for cities in California from the American Community Survey (ACS) using the Census API. The data spans the years 2015 to 2022.

## Data Retrieval
### API Key
The script starts by setting up the necessary API key for accessing the Census API.

### Dataset and Variables
It specifies the datasets and variables required for retrieving income and population data. For income, it uses the 'acs5/profile' dataset with specific variables representing income brackets. For population, it uses the 'acs5' dataset with a variable representing total population.

### FIPS Code and Years
The script defines the FIPS (Federal Information Processing Standards) code for California and a range of years for which data needs to be retrieved.

### API Requests
For each year in the specified range, the script makes API requests for both income and population data. It then processes the retrieved data, including parsing JSON responses, cleaning, and organizing the information into a list.

### Data Transformation
The script transforms the collected data into a Pandas DataFrame. It includes columns for city names, populations, income brackets, and the corresponding year.

### Data Cleaning and Mapping
Column names are mapped to more meaningful names using a predefined dictionary (`column_mapping`). The city names are cleaned by removing the ', California' suffix.

### Data Export
The final DataFrame is exported to a CSV file named 'california_income_by_city_2015_2021.csv', making it suitable for further analysis or integration with other datasets.

---

# California Incomes Data Processing (Year By Year Data Files From Census - california_income_census.ipynb)

## Introduction
This Python script processes income data for the state of California from the years 2015 to 2021. The script combines individual CSV files for each year into a unified dataset and performs data cleaning and formatting operations.

## Data Preparation
### File Organization
The script first defines the list of years and corresponding CSV file names.

### Data Loading and Formatting
The script uses Pandas to load each CSV file into a DataFrame and performs the following operations for each year:
- Converts certain columns to numeric format.
- Processes percentage values to calculate absolute values based on specific percentages.
- Rounds values and adjusts data types.

### Data Reorganization
The script then reorganizes the data by renaming columns, fixing data inconsistencies, and setting appropriate row labels.

## Consolidation
The individual DataFrames for each year are concatenated into a single mega-table, covering the years 2015 to 2021.

## Output
The resulting mega-table is saved as a new CSV file named "california_incomes_2015_2021.csv" for further analysis.

---
# Income x House Price By Year: Population and Housing Analysis (Merging Data - income x house prices.ipynb)

## Introduction
This Python script performs an analysis of population data and housing prices in California. The data is loaded from two CSV files: `PopulationVPrice.csv` for housing prices and `california_income_by_city_2015_2021.csv` for population and income information.

## Data Exploration
The script begins by loading and displaying the first few rows of both datasets to understand their structure.

## Data Preprocessing
### Population Data
- The 'City' column in the population dataset is cleaned to remove ' CDP' suffixes.
- A weighted average income is calculated for each row based on the provided income categories and their corresponding values.

### Pivot Table Creation
A pivot table is created from the population dataset, organizing the average income values by city and year.

## Correlation Analysis
The script calculates the correlation coefficients between average income and housing prices for each year and displays the results. It also generates a line plot of these correlation coefficients over the years.

## Population Analysis
### Total Populations by Income Category
The total populations for each income category are plotted as stacked bar graphs over the years.

### Iterative Bar Graphs
Separate bar graphs are generated for each year, displaying the total populations for each income category. The x-axis labels are rotated for better readability.
=======
Home Price Analysis - Conclusion

Question: Which factors has the greatest effect on a city’s home price?
Violent Crimes, Population, Income, Proximity to Major City, or Unempoyment Rates

After conducting our analysis, it seems that all five variables impact a city’s average home price. However, it is evident that the highest correlation is with the city’s average household income. With an r-value of 0.6529, obtained after removing outliers, it becomes apparent as a city’s average household income increases, so does its average home price.

