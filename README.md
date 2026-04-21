## Experiment 20: Covid-19 Data Analysis

---

### **Aim**
To perform comprehensive exploratory data analysis (EDA) on a global Covid-19 dataset to understand the spread, mortality, and recovery rates across different nations and specific Indian states using Python's data science libraries.

### **Logic**
The core logic involves **Data Cleaning** (removing unnecessary columns and handling missing values), **Data Transformation** (casting dates and integers), **Feature Engineering** (calculating "Active" cases by subtracting deaths and recoveries from total confirmed), and **Data Aggregation** (grouping by country, state, or date to find totals). Finally, **Geospatial Visualization** is used to map the severity of the pandemic globally.

---

### **Theory**
* **Data Wrangling:** The process of cleaning and unifying messy and complex data sets for easy access and analysis.
* **Time Series Context:** Converting `ObservationDate` to a `datetime` object allows for chronological sorting and date-range filtering.
* **Active Cases Formula:**
    $$Active = Confirmed - (Recovered + Deaths)$$
* **Choropleth Maps:** A thematic map where areas are shaded in proportion to the statistical variable being displayed (e.g., more red for higher confirmed cases).

---

### **Algorithm**
1.  **Import** the necessary libraries (`pandas`, `numpy`, `plotly`).
2.  **Load** the dataset from a CSV file.
3.  **Pre-process** the data:
    * Drop irrelevant columns like `SNo` and `Last Update`.
    * Convert column data types to appropriate formats (Date and Integer).
4.  **Calculate** a new feature: `Active = Confirmed - Deaths - Recovered`.
5.  **Filter** for the most recent data using the maximum date in the dataset.
6.  **Aggregate** data using `groupby()` to get total counts per Country and per Province/State.
7.  **Visualize** the results using `plotly.express` for interactive world maps.
8.  **Analyze** specific subsets (e.g., Top 20 countries, India-specific state data).

---

### **One-Liner Explanations**

**Libraries:**
* `import pandas as pd`: Imports the Pandas library for data manipulation and analysis using DataFrames.
* `import numpy as np`: Imports NumPy for high-performance numerical operations and array handling.
* `import plotly.express as px`: Imports Plotly Express for creating high-level interactive visualizations and maps.

**Commands:**
* `pd.read_csv()`: Reads a comma-separated values file into a Pandas DataFrame.
* `data.head()`: Returns the first five rows of the DataFrame to quickly inspect the data.
* `data.drop()`: Removes specified labels (columns or rows) from the DataFrame.
* `data.info()`: Provides a concise summary of the DataFrame, including data types and non-null counts.
* `astype()`: Casts a pandas object to a specified data type (e.g., converting strings to integers).
* `data['Active'] = ...`: Creates a new column based on a mathematical operation between existing columns.
* `data.max()`: Returns the maximum value found in a specific column (used here to find the latest date).
* `groupby()`: Splits the data into groups based on some criteria (like Country) to apply aggregate functions.
* `sum()`: Calculates the arithmetic total of numerical values in a group.
* `reset_index()`: Converts the index of a DataFrame back into a regular column.
* `sort_values()`: Sorts the DataFrame based on the values of one or more columns.
* `fillna()`: Replaces null (NaN) values with a specified placeholder (like "Unknown").
* `px.choropleth()`: Generates a world map where regions are colored based on the data values provided.

---

### **Conclusion**
Through this analysis, we successfully identified the global hotspots of the Covid-19 pandemic. By calculating **Active Cases**, we gained a more accurate picture of the current burden on healthcare systems compared to just looking at total confirmed cases. The visualization confirms that countries like the **US, India, and Brazil** had the highest volumes of cases during the peak, while the state-wise analysis for India highlights **Maharashtra** as a primary area of concern in the regional context.
