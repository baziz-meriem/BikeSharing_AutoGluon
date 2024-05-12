# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### NAME HERE

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
All the predicted outputs had to be non zero.

### What was the top ranked model that performed?
The top ranked model was the model that leveraged more features:
model name : 'WeightedEnsemble_L2
score:-34.374377
fit time:373.145459
pred time:12.043485

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
Key Discoveries from EDA:

Seasonality and Weather Impact: Analysis revealed significant variations in bike rental volumes across different seasons and weather conditions, leading to the inclusion of these features.
Rush Hour Peaks: Rentals peaked during typical rush hours, prompting us to engineer a feature indicating peak and non-peak hours.

Impact on Model Performance:

Initial models lacking these insights (used the datetime attribute as it is and also considers the categorical features as numers) performed worse in terms of RMSE. Incorporating features that captured temporal dynamics (separating the time feature into days month hour and adding the peak time) and treated the categorical features as a categorical features directly improved model accuracy, cause it alowed the model to capture more relationships between the features and the target feature.

### How much better did your model preform after adding additional features and why do you think that is?
Best Model Details:

Model Name: WeightedEnsemble_L2  
RMSE: -34.370879 (This is negative because AutoGluon convert metrics into a format where higher is better, as opposed to lower is better)
improvement_percentage =  (-34.374377 + 52.760495 )/|-34.374377 |*100 = 53.487%

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?

improvement_percentage =  (-38.348396 + 52.760495 )/|52.777176 |*100 = 27.31%
### If you were given more time with this dataset, where do you think you would spend more time?
exploring in details the trends and figure our which features corrolate and which doesn't do only keep relevant features and then try forecasting it will probably yield better results

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.

| Model        | Time Limit (s) | Eval Metric | Hyperparameter Process | Score  |
|--------------|----------------|-------------|------------------------|--------|
| Initial      | 600            | RMSE        | Default                | 1.80720|
| Add Features | 600            | RMSE        | Default                | 0.51901|
| HPO          | 600            | RMSE        | Tuned                  | 0.48045|


### Create a line plot showing the top model score for the three (or more) training runs during the project.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

![model_test_score.png](img/model_test_score.png)

## Summary
In this project, I aimed to predict bike sharing demand using AutoGluon. Through exploratory data analysis, I found that factors like weather conditions, time of day, and holidays significantly affect bike rental patterns, I also found out that Autogluone is Pretty effective at automating the hyperparameter search process, but still needs human intervention for choosing which parameters to tweek, cause it depends on the usecase that's why i think EDA is the most important phase of the ML process (ofcourse after data aquisition) 
Going forward, I plan to refine my feature engineering techniques and explore more advanced modeling approaches to improve accuracy. The project offered valuable insights but also highlighted areas for further development to enhance the predictive performance.
