# Predicting-HDB-Resale-Price

## Background
For individuals exploring resale houses, important considerations such as the storey of the house, location, and property size are crucial. Understanding how these factors affect resale prices and having an estimated price enables informed decision-making when purchasing resale houses. Given the substantial investment that real estate represents for individuals, these understandings are crucial for securing properties aligned with their preferences and financial objectives.
Therefore, is it possible to predict the resale price of a flat based on the prospective owner's preferences (such as location, storey range, floor square area, etc.), enabling them to make informed decisions about their expected expenditure?

## Objectives
This study aims to predict resale prices, providing valuable insights for individuals and enabling informed choices.  

## Setup/Technique Used
The data frame undergoes initial cleaning before any coding or analysis begins. During this process, columns such as "street name" and "lease commence date" were removed, as they were deemed unnecessary. Additionally, the remaining lease is expressed as months.

### Correlation Matrix
Firstly, the analysis aims to determine the correlation between factors such as floor square area, remaining lease duration, and the storey level against resale prices. To visualize these correlations, a correlation matrix was used. Based on the values of the correlations, it was then deduced which factors should be used to create a bi-variate joint plot to assess their suitability as predictors.

### Bi-variate Joint Plot
Outliers were removed using the LocalOutlierFactor(LOF) function before plotting. Subsequently, the R2 values were examined to assess whether the model sufficiently accounted for the variance in the response data around its mean. This evaluation allows one to determine the effectiveness of the model as a predictor.

### Box and Whisker Diagram
To determine if location of the house has an impact on the resale price, a box and whisker plot comparing prices across various towns was employed. This clearly visualizes the distribution of prices, highlighting disparities, if any, in median prices among different towns. Variations in the median suggest that the town could be a contributing factor affecting resale prices.

### Transforming Categorical Variables into Numerical Format
Since the machine learning algorithm requires numerical input variables, it is essential to convert categorical variables (town, flat model, flat type etc.) into a numerical format. The “pd.get_dummies” function in pandas was employed for this purpose. It generates dummy numerical variables by creating new columns for each unique value present in each original categorical column. Each observation is then represented by a combination of “1” and “0” across the newly created columns, where “1” indicates the presence of the specific category and “0” indicates its absence. This transformation allows categorical data to be effectively incorporated into the machine learning algorithm.

### Multi-Variate Prediction
Once the categorical data were converted into numerical format, they can be used in a multi-variate linear regression model. This expands the model's capabilities to capture complex relationships and improve predictive accuracy. Pre-processing steps such as feature scaling and selection were crucial in preparing the dataset for modelling. Without scaling, features with larger magnitudes or ranges may dominate the learning process, resulting in biasness towards those features. Scaling ensures that all features contribute proportionally to the model's learning process, thereby promoting a fair representation, and preventing dominance by any particular feature.

<img width="191" alt="image" src="https://github.com/user-attachments/assets/5352d55d-60ec-4ac2-be02-452225ebfadf">

