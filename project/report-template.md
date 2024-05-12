# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### NAME HERE

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
All the predicted outputs had to be non zero.

### What was the top ranked model that performed?
The top ranked model was the last model the one I tuned with the hyperparameters

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
Key Discoveries from EDA:

Seasonality and Weather Impact: Analysis revealed significant variations in bike rental volumes across different seasons and weather conditions, leading to the inclusion of these features.
Rush Hour Peaks: Rentals peaked during typical rush hours, prompting us to engineer a feature indicating peak and non-peak hours.

Impact on Model Performance:

Initial models lacking these insights performed worse in terms of RMSE. Incorporating features that captured temporal dynamics and treated weather conditions as a categorical feature directly improved model accuracy.

### How much better did your model preform after adding additional features and why do you think that is?
Best Model Details:

Model Name: WeightedEnsemble_L2  
RMSE: -34.370879 (This is negative because AutoGluon convert metrics into a format where higher is better, as opposed to lower is better)

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
looking at the results it seems that it didn't improve which is shoking for me 
improvement_percentage =  (-52.777176 + 34.370879 )/|52.777176 |*100 = -34.87548671%
### If you were given more time with this dataset, where do you think you would spend more time?
exploring in details the trends and figure our which features corrolate and which doesn't do only keep relevant features and then try forecasting it will probably yield better results

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|time|hyperparams search process|score|
|--|--|--|--|
|initial|600|default|1.80274|
|add_features|600|default|0.51901|
|hpo|1000|tuned|1.80274|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

![model_test_score.png](img/model_test_score.png)

## Summary
In this project, I aimed to predict bike sharing demand using AutoGluon. Through exploratory data analysis, I found that factors like weather conditions, time of day, and holidays significantly affect bike rental patterns. 
Going forward, I plan to refine my feature engineering techniques and explore more advanced modeling approaches to improve accuracy. The project offered valuable insights but also highlighted areas for further development to enhance the predictive performance.
