# Food Sales Predictions

### Tijesunimi Odebode

**Description:**

This project involves predicting sales for food items sold at various stores. There are 6 parts in this project. Each part was carried out using python programming language.

**Data Source:**

The data used in this project was retrieved from the following website: https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/


**Part 1:  Loading and verifying data**

In this part, the needed packages were imported and the sales prediction data was loaded and verified

**Part 2: Data Cleaning**

In this part, several steps were carried out to clean the data. Missing values and inconsistent categories of data were addressed. For "Item_Weight" column, the median weight was determined and that median was inserted in the cells with missing value. For the "Outlet_Size" column, the cells with missing values were filled with the most frequent size. Since there were no duplicates in the data, I did not have to address that.
 
**Part 3: Exploratory Data Visualization**

In this section, a histogram, boxplot and heat map were used for exploratory data analysis and visualization. Histogram of the Maximum Retail Price (list price) of products, Boxplot of the 'Item_Weight' column, and Heat map of the 'sales_predictions' dataframe were carried out. 

The histogram showed that the highest number of products fall in the maximum retail price range of roughly 110-125. Also, the histogram showed that no product had a maximum retail price less than approximately 30. Also, no product had a maximum retail price greater than about 268.

From the boxplot, it was apparent that the median for the "Item_Weight" column was approximately around 12.5. The 25th percentile was approximately around 9.3, the 75th percentile was approximately around 16, the minimum was approximately around 4.5 and the maximum was approximately around 21.4. These numbers match up closely with what we see in the summary of statistics table.

It is obvious from the heat map that when you compare each column against itself, you get a correlation value of 1. This is expected. Also, when 'Item_Outlet_Sales' is compared against 'Item_MRP', there is moderate positive correlation with a correlation value of 0.57. This means that the higher the maximum retail price (list price) of the product, the higher the sales of the product in the paricular store, and the lower the maximum retail price (list price) of the product, the lower the sales of the product in the paricular store. The correlation values in the other boxes in the heat map were either less than +0.1(indicating almost no correlation or very weak positive correlation) or they were very weak negative correlation values. Negative correlation indicates that when one column feature goes up, the other column feature being compared with it goes down and vice versa.

**Part 4 - Explanatory Data Visualization**

In this section, outliers in the data set were identified and addressed. Also, using a scatter plot, the 'Item_Visibility' and 'Item_Outlet_Sales' columns were compared to see if there is any correlation between product visibility (the percentage of total display area of all products in a store allocated to the particular product) and sales of the product in the particular store. Finally, using bar charts, the mean of 'Item_Outlet_Sales' column was compared with the 'Item_Fat_Content' column to see if there is any correlation between the fat content of food products and the average sales of products in various stores.

To address outliers, boxplots were utilized. From the boxplots that were created, it was obvious that the following columns had outliers in them: 'Item_Visibility' and 'Item_Outlet_Sales.' The outliers in the 'sales_predictions' data were kept since there was no reason to believe the outliers were an error in the dataset.

For the scatter plot comparison between 'Item_Visibility' and 'Item_Outlet_Sales' columns, no correlation was seen between product visibility (the percentage of total display area of all products in a store allocated to the particular product) and sales of product in the particular store.

For the bar chart comparison between the mean of 'Item_Outlet_Sales' column and the 'Item_Fat_Content' column , it was obvious that the average sales of products in various stores was higher for food products with regular fat content than food products with low fat content.

**Part 5 - Preprocessing for Machine Learning**

In this section, the following tasks were addressed:

a) The target (X) and features (y) were identified. The "Item_Outlet_Sales" column was assigned as the target and the rest of the relevant variables as the features matrix.

b) A train test split was performed

c) A pre processing pipeline was created to prepare the dataset for Machine Learning

After the above tasks were performed, there were no missing values in our data, all numeric data was successfully scaled, ordinal data was ordinal encoded, and nominal data was one-hot encoded.

**Part 6 - Regression Models**

In this section, the following tasks were carried out:

a. A linear regression model was built to predict sales. The performance of the model was evaluated based on R^2. The performance of the model was evaluated based on RMSE.

b. A regression tree model was built to predict sales. The performance of the model was evaluated based on R^2. The performance of the model was evaluated based on RMSE.

c. The model to implement was determined. A justification was provided for the recommendation.

The optimized (max_depth = 6) simple regression tree model seemed to have worked better than the linear regression model. This is because the R^2 and RMSE values indicated less overfitting in the optimized simple regression tree model. The R^2 values of the training and testing sets in the optimized simple regression tree model were closer to each other. Also, the RMSE values of the training and testing sets were closer to each other. The optimized simple regression tree model seemed to perform better on the test set. The following are the results for each model:

a) Linear Regression Model

R^2

Training set = 0.672

Testing set = -5.500e+17

RMSE

Training set = 985.695

Testing set = 1231851641982.857

b) Optimized Simple Regression tree Model

R^2

Training set = 0.616

Testing set = 0.585

RMSE

Training set = 1066.448

Testing set = 1070.531
