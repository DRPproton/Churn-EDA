# Churn-EDA
The provided code is written in Python and aims to perform data exploration and analysis tasks on a given dataset. It begins by importing the necessary libraries, including pandas, numpy, matplotlib. pyplot, and seaborn. These libraries provide data manipulation, analysis, and visualization functionalities, which will be utilized throughout the code.

After importing the libraries, the code sets the options to display all rows and columns of the dataset. Doing so ensures that no data is truncated, especially if the dataset is large and the default display settings limit the number of rows and columns shown.

Next, the code reads the dataset from a CSV file, creating a pandas DataFrame named 'df' to store the data. This data frame is the primary data structure for subsequent operations and analysis.

The code explores various aspects to gain initial insights into the dataset's shape and content. It displays the first five rows of the DataFrame, providing a sample of the data. Additionally, it outputs the number of rows and columns in the dataset, which helps understand the data's overall size and dimensionality.

To better understand the numerical variables in the dataset, the code generates summary statistics using the 'describe()' function provided by pandas. This function calculates various statistical measures for each numerical column, such as minimum, maximum, mean, median, and quartiles. These statistics provide an overview of the data distribution and central tendencies.

Moving forward, the code checks for null values within the dataset. It employs the 'isnull()' function to identify columns with missing values and counts the number of null values in each column using the 'sum()' function. This step helps assess the completeness of the dataset and identify potential data gaps or inconsistencies.

Upon identifying columns with null values, the code handles them appropriately. In this specific case, the 'InternetService' column is found to have some missing values. To address this, the code replaces the null values with the string 'NIS,' which stands for "No Internet Service." This transformation ensures that the missing values are appropriately labeled and accounted for during subsequent analysis.

The code checks for duplicate entries within the dataset to ensure data integrity and identify any potential data duplication. It employs the 'duplicated()' function, which returns a boolean series indicating whether each row is a duplicate of a previous row. By summing the values of this series, the code determines the total number of duplicated rows. If duplicates are found, additional steps could be taken to handle or remove them. However, there are no duplicated entries within the dataset in this case.

Next, the code focuses on preparing the data for further analysis. It converts specific object columns, which likely represent categorical variables, to the category data type using the 'as type ()' function. This conversion optimizes memory usage and allows for efficient categorical operations. By looping over the columns of the DataFrame, the code identifies object columns and converts them to the category data type.

Furthermore, the code modifies the order of ordinal categorical data present in the question variables. It assigns a custom categorical data type, 'q_ans_order,' which follows the order of importance for the question variables (1 = most important, 8 = least important). By applying this custom data type to the respective columns, the code ensures that subsequent analyses consider the correct ordinal order when dealing with these variables.

After modifying the data types and order, the code drops specific columns that are deemed unnecessary for further analysis. By using the 'drop()' function, the code removes columns such as 'CaseOrder,' 'Customer_id,' 'Interaction,' 'UID,' 'Lat,' 'Lng,' 'Zip,' 'Population,' and 'TimeZone' from the DataFrame. This step helps streamline the dataset and focus on the relevant variables.

The code generates summary statistics and visualizations to gain insights into the distribution of the numerical variables. The 'get_summary_stats_by_columns()' function is used to calculate summary statistics for numerical variables, such as minimum, maximum, quartiles, mean, median, mode, unique value count, standard deviation, skewness, and kurtosis. These statistics provide a comprehensive overview of the numerical data distribution.

Furthermore, the code employs the 'hist()' function from matplotlib.pyplot to generate histograms for all numerical variables. These histograms visualize the frequency distribution of each variable and provide initial insights into the shape and spread of the data. The histograms help identify potential outliers or unusual patterns within the numerical variables.

The code generates boxplots using the 'boxplot()' function from Seaborn to investigate potential outliers in numerical variables. Boxplots display the data distribution, including outliers, quartiles, and median values. By visually examining the boxplots, the code identifies variables with potential outliers. For example, the 'Children' and 'Income' variables are analyzed using boxplots to assess the presence of outliers. If outliers are detected, appropriate measures can be taken to handle them, such as imputing or removing them.

Moving on to categorical variables, the code performs analysis and visualization to understand the distribution and frequencies of different categories. Using the 'describe()' function on columns with non-numeric data types, the code generates descriptive statistics specifically for categorical variables. These statistics include the count, unique value count, top category, and frequency of the top category.

To visualize the categorical variables, the code employs bar charts using Seaborn's 'counterplot ()' function. It iterates over the categorical columns, generates a count plot for each column, and labels the x-axis ticks appropriately to enhance readability. The bar charts display the frequency of each category within the categorical variables, providing insights into the data distribution and potential imbalances.

The code explores the relationship between the Churn and other numerical and categorical variables. Bivariate analysis is performed to understand how the 'Churn' variable varies concerning different attributes. The code generates boxplots and bar charts to compare the distributions and frequencies of variables grouped by the 'Churn' variable.

For numerical variables, boxplots are used to compare the distributions of each variable between customers who churned and those who did not. By visually examining the boxplots, the code identifies potential differences in the distributions that may indicate a relationship between the variable and Churn.

Regarding categorical variables, bar charts display the frequency of each category within the variable for both churned and non-churned customers. By comparing the bar heights between the two groups, the code allows for a visual assessment of potential differences in category frequencies, providing initial insights into the relationship between the categorical variables and churn.

The code tests the hypothesis using the chi-squared test to investigate further the relationships between the 'Churn' variable and categorical variables. The chi-squared test determines whether there is a significant association between two categorical variables. By applying the 'chi2_contingency()' function to contingency tables created from the 'crosstab()' function, the code calculates the chi-squared statistic and the corresponding p-value for each variable.

The code then determines whether the null hypothesis can be rejected based on the calculated p-values. If the p-value is below a significance level (e.g., 0.05), the null hypothesis is rejected, suggesting a significant relationship between the variable and Churn. Conversely, if the p-value is above the significance level, the null hypothesis is not rejected, indicating any significant relationship.

Additionally, the code calculates point-biserial correlation coefficients and p-values to measure the correlation between the 'Churn' variable and numerical variables. Point-biserial correlation assesses the relationship between a binary variable ('Churn') and a continuous variable. By employing the 'point biserial ()' function from scipy.stats, the code calculates the correlation coefficients and p-values for each numerical variable.

In conclusion, the provided code comprehensively analyzes the dataset, exploring the distributions, relationships, and correlations between variables. It handles missing values, data types, and outliers, providing meaningful visualizations and statistical measures. Through hypothesis testing and correlation analysis, the code identifies variables significantly related to the 'Churn' variable, aiding in understanding factors influencing customer churn.
