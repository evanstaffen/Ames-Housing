# King County Housing Dataset
![SunsetView.png](https://github.com/evanstaffen/Ames-Housing/blob/main/Images/SunsetView.png)

## Business Problem
The Johnson's recently had their first child. While they have loved living in New York City, they've decided that they would like a slower paced lifestyle and more space for their kid. I have been assigned to help them find a house that matches their needs, is affordable and in King County, Washington. I will be creating a predictive algorithm that will show the zip codes that the Johnson family could afford to buy a house

![KCMap.png](https://github.com/evanstaffen/Ames-Housing/blob/main/Images/KCMap.png)
![MainStreet.png](https://github.com/evanstaffen/Ames-Housing/blob/main/Images/MainStreet.png)

## Dataset
I used the King County House Sales dataset for this analysis, which can be found in the data folder of this repository. As well, there is a summary of the columns in the dataset in the data folder as well labelled ‘column_names.md’.

## Data Cleaning and Preparation
The first step I took was to scan through the dataset and see if there were any significant missing values or errors within it. 
•	Columns with outliers/imputation errors that were replaced or dropped
o	bedrooms, price, sqft_basement, waterfront, yr_renovated
•	The date column was separated into day, month and year
o	This ultimately didn’t end up proving to be significant
•	All columns containing sqft in their name were changed from integers to floats, while bathrooms and floors were changed from objects to integers
•	The grade column was split into a rating column and condition column
•	All zip codes that are in Seattle were dropped from this analysis
•	The nominal (waterfront, zip codes) and ordinal variables (view,condition)

## Methods
A baseline model was created first based on which predictor has the highest correlation. Since sqft_living had the R2, I used it solely as a model to build off of. As expected, the correlation coefficient was very low (0.53) and was not good at predicting the price of a house on its own. 

## Modeling and Regression
Five models were created for this project. Ultimately, the 4th model did end up being the best predictor. Below shows the MAE, RMSE and R2 values for each model (except the 1st model)

The correlation coefficients were as follows:
Only sqft_living
1st model R2: 0.534

All predictor variables, encoding nominal and categorical variables
2nd model R2: 0.663 
2nd model test R2: 0.667
MAE: 116395.59
RMSE: 164150.50

Encoding zip codes
3rd model R2: 0.867
3rd model test R2: 0.866
MAE: 69883.59
RMSE: 104065.81

Applying log transformation to price
4th model R2: 0.888
4th model test R2: 0.874
MAE: 61646.16
RMSE: 107207.96

Remove multicollinearity by not using all sqft columns
5th model R2: 0.882
5th model test R2: 0.877
MAE: 63776.51
RMSE: 113147.92

## Comparing the 2nd and 5th models
Model 2:
![Model2Distplot.png](https://github.com/evanstaffen/Ames-Housing/blob/main/Images/Model2Distplot.png)
![Model2QQplot.png](https://github.com/evanstaffen/Ames-Housing/blob/main/Images/Model2QQplot.png)

Model 5:
![Model5Distplot.png](https://github.com/evanstaffen/Ames-Housing/blob/main/Images/Model5Distplot.png)
![Model5QQplot.png](https://github.com/evanstaffen/Ames-Housing/blob/main/Images/Model5QQplot.png)

The correlation coeficient increased from 0.663 all the way to 0.882, with a final RMSE (or average error) of $113,000. The final model is clearly a much better predictor of the housing prices in the King County suburb area. The last model was picked over the fourth model because it excluded the collinear variables and the training and test correlation coefficients were closer to one another. 

## Conclusions + Recommendations
•	King County is an affordable place for the Johnson’s to move to
•	In fact, they may be able to get a house even cheaper than they were expecting

## Next Steps
•	Try finding data pertaining to the nearest towns/attractions, quality of schools and hospitals
•	Find data more recently than 2014-2015

├── data
├── images
├── .gitignore
├── Housing Market Analysis Slides.pdf
├── Housing Market Linear Regression.ipynb
└── README.md

![image](https://user-images.githubusercontent.com/113449546/198918449-46c5f4ad-a7d8-4dae-9e08-143290ef08f8.png)
