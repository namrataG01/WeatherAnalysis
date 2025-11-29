# Weather Forecast Data Analysis

This project analyzes a weather forecast dataset using Python libraries such as pandas, numpy.

## Dataset Overview

The dataset file is `weather_forecast_data.csv` and contains 2,500 rows and 6 columns:

- **Temperature** (float): Measured in degrees
- **Humidity** (float): Percentage
- **Wind_Speed** (float): Speed in km/h (assumed unit)
- **Cloud_Cover** (float): Percentage
- **Pressure** (float): Atmospheric pressure (assumed hPa)
- **Rain** (object): 'rain' or 'no rain'

## Data Exploration Steps

### 1. Loading the Dataset

```python
import pandas as pd
df = pd.read_csv("/content/weather_forecast_data.csv")
```

### 2. Initial Data Exploration

- `df.head()` : Shows the first 5 rows
- `df.info()` : Provides info about columns, data types, and non-null counts
- `df.shape` : Reveals (rows, columns) count
- `df.describe()` : Shows summary statistics for numeric columns
- `df.index` : Displays row index info
- `df.columns` : Lists column names
- `df.dtypes` : Shows each column's data type

### 3. Uniqueness and Counts

- `df['Column'].unique()` : All unique values in the column
- `df.nunique()` : Number of unique values for each column
- `df.count()` : Non-null count per column
- `df['Rain'].value_counts()` : Counts of 'rain' and 'no rain' entries

#### Example Output:
```
Rain
no rain    2186
rain        314
dtype: int64
```

### 4. Query Examples

- Find all unique 'Wind_Speed':
  ```python
  df['Wind_Speed'].unique()
  ```
  There are 2,500 unique wind speed values.

- Get number of times when there _is_ rain:
  ```python
  df[df.Rain == 'rain']
  ```
  There are 314 occurrences of rain.

- Find all null values:
  ```python
  df.isnull().sum()
  ```
  Every column has 0 nulls.

- Rename 'Cloud_Cover' to 'cloud_info':
  ```python
  df.rename(columns = {'Cloud_Cover' : 'cloud_info'})
  ```
  Note: This returns a new DataFrame; use `inplace=True` if you want to update the original.

### 5. Basic Statistics

- Mean Humidity:
  ```python
  df['Humidity'].mean()
  # 64.34709445763546
  ```
- Standard deviation of Pressure:
  ```python
  df['Pressure'].std()
  # 20.19643279398678
  ```

## Requirements

- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- statsmodels
- scikit-learn

## Usage

You can run the code snippets in [Google Colab](https://colab.research.google.com/) or locally after installing required packages.

## License

MIT License

## Author

namrataG01
