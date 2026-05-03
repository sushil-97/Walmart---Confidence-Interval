# Walmart---Confidence-Interval
# Walmart Sales Data Analysis Project

## Project Overview
This project focuses on analyzing sales data from Walmart to understand customer purchasing behavior. The goal is to perform exploratory data analysis, identify key trends, and draw conclusions regarding different customer segments, such as gender and marital status, to provide actionable recommendations for Walmart.

## Dataset
The analysis uses a Walmart sales dataset, loaded from a CSV file. The dataset includes information on `User_ID`, `Product_ID`, `Gender`, `Age`, `Occupation`, `City_Category`, `Stay_In_Current_City_Years`, `Marital_Status`, `Product_Category`, and `Purchase` amount.

## Data Loading and Initial Exploration

### 1. Data Loading
- The `walmart_data.csv` file was uploaded and loaded into a pandas DataFrame.

### 2. Initial Data Inspection
- `df.head()`: Displayed the first 5 rows to get a glimpse of the data structure.
- `df.describe()`: Provided descriptive statistics for numerical columns, indicating the distribution and potential range of values.
- `df.info()`: Showed data types and non-null counts, confirming no missing values in the dataset.
- `df.isnull().sum()`: Explicitly checked for null values, confirming a clean dataset with no missing entries.
- `df.nunique()`: Counted unique values per column.
- `df.select_dtypes(include='object').columns`: Displayed value counts for categorical columns to understand their distributions.

## Exploratory Data Analysis (EDA)

### Univariate Analysis
- **Countplots**: Visualized the distribution of categorical variables (`Gender`, `Age`, `City_Category`, `Stay_In_Current_City_Years`, `Marital_Status`) using `seaborn.countplot` to understand the frequency of each category.

### Bivariate Analysis
- **Boxplots**: Examined the relationship between `Purchase` amount and categorical variables (`Gender`, `Age`, `City_Category`, `Stay_In_Current_City_Years`, `Marital_Status`) using `seaborn.boxplot`. This helped in understanding the spread and central tendency of purchase amounts across different groups.
- **Correlation Heatmap**: Analyzed the correlation between numerical variables (`Occupation`, `Marital_Status`, `Purchase`, `Product_Category`) using `seaborn.heatmap` to identify linear relationships.

### Outlier Detection
- **Boxplots for Numerical Columns**: Used boxplots to visualize potential outliers in numerical features (`Occupation`, `Marital_Status`, `Product_Category`, `Purchase`).

## Confidence Interval Analysis

The Central Limit Theorem was applied to calculate confidence intervals for average purchase amounts, and observations were reported for different confidence levels (90%, 95%, 99%).

### 1. Overall Confidence Interval
- A 95% confidence interval for the overall average spending was calculated, indicating that the true population average lies between approximately 9250.69 and 9277.24.

### 2. Gender-based Confidence Interval
- **Average Purchase**: Male customers have a higher average purchase amount (approx. 9437.53) compared to female customers (approx. 8734.57).
- **Confidence Intervals**: Separate confidence intervals were calculated for male and female customers for 90%, 95%, and 99% confidence levels. It was observed that these confidence intervals **do not overlap**.

### 3. Marital Status-based Confidence Interval
- **Average Purchase**: The average purchase amounts for married and unmarried customers are very close (unmarried: approx. 9265.91, married: approx. 9261.17).
- **Confidence Intervals**: Separate confidence intervals were calculated for married and unmarried customers. These confidence intervals **overlap**, suggesting no statistically significant difference in average spending between these groups.

### 4. Age-based Confidence Interval (Planned but not yet implemented in provided notebook)
- *This section would involve binning age groups and repeating the confidence interval analysis similar to Gender and Marital Status.*

## Key Findings and Recommendations for Walmart

### Based on Gender Analysis:
- **Finding**: Male customers, on average, spend significantly more per transaction than female customers, with non-overlapping confidence intervals.
- **Recommendations for Male Customers**:
    - Promote high-value items, potentially in categories where men show higher spending (e.g., electronics, tools, automotive, specific apparel).
    - Implement reward programs tailored to male purchasing habits.
    - Conduct further analysis to understand specific product categories or features that drive higher spending among men.

- **Recommendations for Female Customers**:
    - Focus on promotions and offers for family-based products and aesthetic items.
    - Analyze purchase frequency and patterns to provide personalized shopping experiences and targeted promotions.

### Based on Marital Status Analysis:
- **Finding**: The average spending between married and unmarried customers is not statistically different, as their confidence intervals overlap.
- **Recommendations**:
    - Walmart should look beyond marital status for significant differentiators in purchasing behavior.
    - Focus on other behavioral aspects like frequency of visits, preferred product categories, and online vs. in-store shopping habits.
    - If further analysis on married customers is desired, investigate purchases of home-related items or family-oriented products, which might reveal valuable insights for targeted promotions, rather than focusing solely on overall average spend.