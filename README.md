# Programming Assignment 4: Data Wrangling and Data Documentation
This repository contains Python script for analyzing student performance based on data from an Excel file. The script performs data filtering and generate visualizations using Seaborn and Matplotlib.

### Prerequisites
Make sure you have the following Python libraries installed:
* pandas
* seabon
* matplotlib

### Script Overview
**1. Data Loading:**
```python
import pandas as pd

df = pd.read_excel('board2.xlsx')
df
```
This loads the Excel file into a DataFrame named `df`.

**2. Data Filtering:**
```python
Instru = df[(df["Track"] == "Instrumentation") & (df["Hometown"] == "Luzon") & (df["Electronics"] > 70)][["Name", "GEAS", "Electronics"]]
Instru
```
This filters `df` with students in the "Instrumentation" track from "Luzon" with Electronics scores greater than 70 and selects relevant columns.

```python
Mindy = df[(df["Hometown"] == "Mindanao") & (df["Gender"] == "Female") & (df["Average"] >= 55)][["Name", "Track", "Electronics", 'Average']]
Mindy
```
This filters `df` with female students from "Mindanao" with an average grade of 55 or higher and selects relevant columns.

**3. Data Visualization:**
```python
import seaborn as sns
import matplotlib.pyplot as plt

plt.figure(figsize=(10, 5))

# Bar plot for Track
plt.subplot(3, 1, 1)
sns.barplot(x='Track', y='Average', data=df)  
plt.title('Average Grade by Track')

# Bar plot for Gender
plt.subplot(3, 1, 2)
sns.barplot(x='Gender', y='Average', data=df)  
plt.title('Average Grade by Gender')

# Bar plot for Hometown
plt.subplot(3, 1, 3)
sns.barplot(x='Hometown', y='Average', data=df) 
plt.title('Average Grade by Hometown')

plt.tight_layout()
plt.show()
```
This creates and displays three bar plots showing average grades by Track, Gender, and Hometown.

## Explanation of Script
### ECE Board Exam Problem:

**Objective:**
To analyze student performance data using data wrangling and visualization techniques, presenting different DataFrames and visuals to provide insights into the dataset.

**Dataset**
The dataset `board2.xlsx` contains student performance data with columns such as `Name`, `Math`, `Electronics`, `GEAS`, `Communication`, `Track`, `Hometown`, `Gender`, and `Average`.

**Data Wrangling**
```python
import pandas as pd

df = pd.read_excel('board2.xlsx')
df
```
* `import pandas as pd`: Imports the pandas library.
* `df = pd.read_excel('board2.xlsx')`: Reads the excel file `board2.xlsx` into a DataFrame named `df`.
* `df`: A call to display the DataFrame, showing the contents of the Excel file.

**A. Filtering for Instrumentation Track from Luzon**
```python
Instru = df[(df["Track"] == "Instrumentation") & (df["Hometown"] == "Luzon") & (df["Electronics"] > 70)][["Name", "GEAS", "Electronics"]]
Instru
```
* `df[...]`: Filters the DataFrame based on the conditions specified within the brackets.
*  `df['Track'] == 'Instrumentation'`: Checks if the value of 'Track' column is 'Intrumentation'.
*  `df['Hometown'] == 'Luzon'`: Checks if the value in the 'Hometown' colums is 'Luzon'.
*  `df['Electronics'] > 70`: Checks if the value in the 'Electronics' column is greater than 70.
*  `[['Name','GEAS','Electronics']]`: Selects only the 'Name', 'GEAS', and 'Electronics' columns from the filtered DataFrame.
*  `Intsru`: A call to display the resulting DataFrame that matches the given condition.

**B. Filtering Female Students from Mindanao**
```python
Mindy = df[(df["Hometown"] == "Mindanao") & (df["Gender"] == "Female") & (df["Average"] >= 55)][["Name", "Track", "Electronics", 'Average']]
Mindy
```
* `df[...]`: Filters the DataFrame based on the specified conditions.
* `df['Hometown'] == 'Mindanao'`: Checks if the value in the 'Hometown' column is 'Mindanao'.
* `df['Gender'] == 'Female'`: Checks if the value in the 'Gender' column is 'Female'.
* `df['Average'] >=  55`: Checks if the value in the 'Average' column is greater than or equal to 55.
* `[['Name', 'Track', 'Electronics', 'Average']]`: Selects only the 'Name', 'Track', 'Electronics', and 'Average' columns from the DataFrame.
* `Mindy`: A call to display the resulting DataFrame that meets the given conditions

**Data Visualization**
```python
import seaborn as sns
import matplotlib.pyplot as plt

plt.figure(figsize=(10, 5))
```
* `import seaborn as sns`: Imports the Seaborn library for the statistical data visualization
* `import matplotlib.pylplot as plt`: Imports Matplotlib's pyplot module visualizations.
* `plt.figure(figsize=(10,5))`: Creates a new figure with a specified size of 10 inches wide by 5 inches high.

**A. Bar Plot for Track**
```python
plt.subplot(3, 1, 1)
sns.barplot(x='Track', y='Average', data=df)  
plt.title('Average Grade by Track')
```
* `plt.subplot(3,1,1)`: Creates a subplot in a 3 row by 1 column grid, selecting the first boxplot.
* `sns.barplot(x='Track', y='Average', data=df)`: Creates a bar plot with 'Track' on the x-axis and 'Average' on the y-axis, using the DataFrame `df`.
* `plt.title('Average Grade by Track')`: Sets the title of the plot.

**B. Bar Plot for Gender**
```python
plt.subplot(3, 1, 2)
sns.barplot(x='Gender', y='Average', data=df)  
plt.title('Average Grade by Gender')
```
* `plt.subplot(3,1,2)`: Creates a subplot in the second position of a 3 row by 1 column grid.
* `sns.barplot(x='Gender', y='Avergae', data=df)`: Creates a bar plot with 'Gender' on the x-axis and 'Average' on the y-axis.
* `plt.title('Average Grade by Gender'): Sets the title of the plot.

**Bar Plot for Hometown**
```python
plt.subplot(3, 1, 3)
sns.barplot(x='Hometown', y='Average', data=df) 
plt.title('Average Grade by Hometown')
```
* `plt.subplot(3,1,3)`: Creates a sublot in the third position of a 3 row by 1 column grid.
* `sns.barplot(x='Hometown', y='Average', data=df)`: Creates a bar plot with 'Hometown' on the x-axis and 'Average' on the y-axis.
* `plt.title('Average Grade by Hometown')`: Sets the title of the plot.

```python
plt.tight_layout()
plt.show()
```
* `plt.tight_layout()`: Adjusts the spacing of the subplots to fit within the figure area.
* `plt.show()`: Displays the bar plots.

This script loads bar takers data, perform various filters to extract specific subsets, and creates visualizations to analyze average grades across different categories.

### Notes
* Ensure that the board2.xlsx file is in the same directory as the script or provide the full path to the file.

### Profile
**Author:** Czarina Julia C. Cueco

*I am currently an engineering student from University of Santo Tomas, working with data analysis and data visualization using Pandas, Seabon, and Matplotlib in Python. This repository is part of a programming assignment, where I explore how to load and manipulate data, data wrangling, and data visualization.*

### Edit History
| Date           | Description                                           |
|----------------|-------------------------------------------------------|
| 2024-09-18     | Initial Creation                                      |

  
