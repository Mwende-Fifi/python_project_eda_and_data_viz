# Python Project EDA & Data Viz - AirBnB Listing 2024(New York)

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools/libraries](#tools/libraries)
- [Data Cleaning/Preparation](#data-cleaning/preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results/Findings](results/findings)
- [Recommendations](recommendations)
- [Limitations](limitations)
- [References](references)
  
### Project Overview
This project aims to conduct a comprehensive EDA on the New York Airbnb 2024 dataset, utilizing Python libraries such as Pandas, NumPy, Seaborn, and Matplotlib. 
By delving into the data, we will uncover valuable insights into Airbnb listings, pricing trends, and guest preferences in New York City.


![output](https://github.com/user-attachments/assets/e1d0e2a6-714c-406c-90ce-258862a03c6a)


### Data Sources

EDA data - The New York Airbnb 2024 dataset ("datasets.csv") contains over 20,000+ records, providing detailed information about Airbnb listings in New York City.

### Tools/libraries

**Programming language**: Python

- Pandas - Data manipulation and analysis
- NumPy - Numerical operations
- Seaborn - Statistical data visualization
- Matplotlib - General-purpose plotting

**IDE (Integrated Development Environment):**
- Jupyter Notebook or a similar environment is commonly used for data analysis and visualization projects. It provides a convenient interface for writing and executing code, and for viewing the output.
- 
### Data Cleaning/Preparation

1. **Identifying Missing Values**:
   - data.isnull().sum(): Calculates the count of missing values in each column of the DataFrame data.
2. **Dropping Missing Values**:
   - data.dropna(inplace=True): Removes rows containing any missing values from the DataFrame data and modifies the original DataFrame in-place.
3. **Handling Missing Values (Alternative)**:
   - data.fillna(): Fills missing values with specified values or strategies (e.g., mean, median, mode). 
4. **Identifying Duplicate Rows**:
   - data.duplicated().sum(): Counts the number of duplicate rows in the DataFrame data.
5. **Dropping Duplicate Rows**:
   - data.drop_duplicates(inplace=True): Removes duplicate rows from the DataFrame data and modifies the original DataFrame in-place.
6. **Type Casting**:
   - data['id'] = data['id'].astype(object): Converts the data type of the 'id' column to 'object' (likely to accommodate string or mixed data).
   - data['host_id'] = data['host_id'].astype(object): Converts the data type of the 'host_id' column to 'object'.

### Exploratory Data Analysis

Here are some questions you can derive from the EDA section:

**Identifying Outliers**:
- **Are there any listings with extremely low prices (less than $1500)?** This could indicate data entry errors or unusual properties.
- **What is the overall distribution of the "price" variable?** Are there any significant skews towards high or low prices?

**Price Distributions**:
- **How are prices distributed across different price ranges?** Are there clusters or gaps in the distribution?
- **Is the price distribution similar for listings with different availabilities (availability_365)?**

**Price per Bed**:
- **Is there a relationship between price and room type (entire home/apt, private room, shared room)?** Do entire homes/apartments typically command a higher price?
- **Is there any variation in this relationship across different neighborhood groups?**

**Number of Reviews and Price**:
- **Is there a correlation between the number of reviews and price?** Do listings with more reviews generally have higher prices?
- **Does this relationship vary across different neighborhood groups?**

**Relationships between Variables**:
- **Do any of the numerical variables (price, minimum nights, number of reviews, availability, number of beds) exhibit strong positive or negative correlations with each other?** This can help identify potential relationships between factors.

**Geographical Distribution**:
- **How are AirBnB listings geographically distributed across the city (based on latitude and longitude)?** Are they concentrated in specific areas?
- **Do different room types (entire home/apt, private room, shared room) have distinct geographical distributions?**

**Correlations and Heatmap**:
- **Which numerical variables have the strongest positive or negative correlations with price?** This can highlight factors influencing pricing the most.
- **Are there any surprising correlations between the variables?** This can lead to further investigation into potential relationships.

### Data Analysis

Including some interesting code/features I worked with:

```python
# Geographical Distribution of AirBnB listing

plt.figure(figsize=(10,7))
sns.scatterplot(data=df, x='longitude', y='latitude', hue='room_type')
plt.title('Geographical Distribution of AirBnB listing')
plt.show()
```
```python
#Price Distributions
data['price']
plt.figure(figsize=(6, 3))
sns.histplot(data=df, x='availability_365')
plt.title('availability_365 Distribution')
plt.ylabel("Frequency")
plt.show()
```

### Results/Findings

**Summary of Results from the New York Airbnb 2024 EDA**

**Data Cleaning and Preparation**:
- The dataset was cleaned by handling missing values and removing duplicates.
- Data types were adjusted as necessary.

**Exploratory Data Analysis**:
- **Price Distribution**: The distribution of prices was found to be skewed to the right, indicating a concentration of listings at lower prices with a few high-priced outliers.
- **Relationship between Price and Availability**: There was no strong correlation between price and availability, suggesting that price is not heavily influenced by availability.
- **Price per Bed**: Prices per bed varied across different neighborhood groups, with some areas offering better value for money.
- **Room Type and Price**: Entire home/apartments generally commanded higher prices compared to private rooms or shared rooms, but this relationship might vary across neighborhoods.
- **Number of Reviews and Price**: A positive correlation was observed between the number of reviews and price, suggesting that listings with more reviews tend to have higher prices.
- **Geographical Distribution**: Listings were clustered in certain areas of the city, with variations in distribution based on room type.
- **Correlations**: The heatmap revealed correlations between price and factors like minimum nights, number of reviews, and availability, indicating their influence on pricing.

### Recommendations

Based on the analysis and findings summarized, here are some recommendations to further enhance the project:

**1. Explore Guest Demographics**:
- **Analyze guest data (if available)**: If the dataset includes guest information, explore the relationship between guest demographics (e.g., age, nationality) and listing preferences.
- **Identify target markets**: Identify specific guest segments that might be more interested in certain types of listings or neighborhoods.

**2. Comparative Analysis**:
- **Analyze trends over time**: Examine changes in pricing, availability, and guest preferences over different periods.
- **Seasonal patterns**: Identify seasonal variations in demand and pricing.

**3. Guest Satisfaction Analysis**:
- **Utilize review data**: Analyze guest reviews to identify areas for improvement and measure overall guest satisfaction.
- **Sentiment analysis**: Employ sentiment analysis techniques to gauge the sentiment expressed in reviews.

### Limitations

One potential limitation of this project could be the availability and quality of data.

- **Data Completeness**: The New York Airbnb 2024 dataset might have missing or incomplete data, which can affect the accuracy of your analysis.
- **Data Bias**: The data might be biased in terms of the types of listings included or the demographics of the guests.

### References

1. [Data Science from Scratch, 2nd Edition](https://www.oreilly.com/library/view/data-science-from/9781492041122/)
