# At Risk Stroke Prediction
 
**Zach Hanson**

### Business problem:
In this problem we are trying to predict whether or not a person is at risk of a stroke based on various health and environmental factors.

### Data
#### Source:
Data obtained from: https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset

For this data set there is 5,110 rows, and 11 columns. 

#### Data Dictionary:
![alt text](https://github.com/Zach-Hanson3/At-Risk-Stroke-Prediction/blob/main/photo_directory/datadict.PNG)



## Methods
- Remove unnecessary columns
    - ID column was dropped, not important to our predictions as each entry is a unique identifier for the patient.
- Check unnecessary rows
    - Missing values in 'bmi' column, will be addressed in preprocessing
- Dataframe was copied for use in exploratory analysis
- Create boxplot of all the categorical columns to view their distributions
- Create boxplot of all the numerical columns to view their distributions
- Create heatmap showing the correlations between all of the numerical data and our target column, stroke
- Create bar charts of the remaining categorical data and seeing the distributions when grouped by stroke column
- Create a more detailed bar chart of Stroke vs. Smoking Status to investigate this relationship more closely
- Create a more detailed bar chart of Stroke vs. Age to investigate this relationship more closely
- Dataframe was copied again for use in machine learning
- Data was split into training and testing sets
- Create a pipeline to impute the missing numerical data, then scale or OneHotEncode all of the data, depending on the type (Numerical or Categorical)
- Created and tuned a Decision Tree Classifier model
- Created and tuned a KNN model
- Created and tuned a Random Forest Classifier model
- Created and tuned a Random Forest Classifier with PCA model
- Created and tuned a KNN with PCA model
- Compared recall and accuracy testing scores between all of our models
- Made a recommendation based on recall testing scores


## Results
### Exploratory Data Analysis
![alt text](https://github.com/Zach-Hanson3/At-Risk-Stroke-Prediction/blob/main/photo_directory/Correlation_Heatmap.PNG)

- No very strong correlations between Stroke and any of the other features.
    - However, weak positive correlation between Age and Stroke
- Other noteable correlations:
    - Strong positive correlation between "age" and "ever_married"
    - Weak positive correlation between "age" and "bmi"
    - Weak positive correlation between "ever_married" and "bmi"
    

### Explanatory Data Analysis
![alt text](https://github.com/Zach-Hanson3/At-Risk-Stroke-Prediction/blob/main/photo_directory/Stroke%20vs%20Smoking%20Trend.PNG)

- More non-smokers have not had strokes compared to current and former smokers.
- People that have had a stroke are slightly more likely to currently or formerly smoke than non-smokers.
- If the unknown entries were discovered, it may swing the data more drastically in one direction.
    - This effect most likely be most impactful in the "yes" category with such a small amount of data
    
    


![alt text](https://github.com/Zach-Hanson3/At-Risk-Stroke-Prediction/blob/main/photo_directory/Age%20vs%20Stroke%20Trend.PNG)

- People who did not have a stroke have a fairly average age of just over 40 years old.
- People who did have a stroke have a median age of just over 70.
- We can see the median age of people who have had a stroke is much higher, about 30 years, than people who have not had a stroke.




## Model
### Models Used:
- Decision Tree Classifier
- K-Nearest Neighbors
- Random Forest Classifier
- Random Forest Classifier with PCA
- K-Nearest Neighbors with PCA

### Results of Models
![alt text](https://github.com/Zach-Hanson3/At-Risk-Stroke-Prediction/blob/main/photo_directory/model%20performance.PNG)

## Recommendations

### Model Recommendation:
- We want to minimize the amount of type 2 errors (False Negative), so we want the model with the highest recall.
- The model with the highest recall score is the Random Forest Classifier.
- This model has a recall score of 72.5%. This means it can successfully identify whether or not a person is at risk for a stroke 72.5% of the time.
- The optimal parameters for this model are:
    - max_depth = 5
    - min_samples_leaf = 1
    - min_samples_split = 5
    - n_estimators = 7
    - Decision Threshold of 0.05


## Limitations & Next Steps
- While this model was the best out of all the tested models, there is still quite a bit of error when it comes to predicting a health risk like stroke.
- Acquiring more data, more specifically information on people who have had strokes, would be helpful in making this model more accurate.
    - Only about 250 out of the 5,110 total data points had recorded a stroke.
    - This is only about 5% of our overall data and could be skewed by any small outliers.


### For further information

For any additional questions, please contact **zhansonpdx@gmail.com**
