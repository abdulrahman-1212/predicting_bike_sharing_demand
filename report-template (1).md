# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Abdulrahman Mahmoud

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
I had to fix some syntax errors and review additional documentation in order to run the model as intended. I had some trouble starting the tasks on my local environment and I decided to do everything in the SageMaker studio and managed to improve my results and get a score of below 0.6 while in the beginning I only managed to get scores of above 1.8.

### What was the top ranked model that performed?
predictor_new_features was the top ranked model.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
EDA gave me insights about data, helped me understand it better, and helped me answer the question "Are there any correlated data?". It turned out that the datetime column needded to be split track the data more closely.
### How much better did your model preform after adding additional features and why do you think that is?
adding additional features had a magical effect on the accuracy of the model. The score dropped from 1.8 to 0.533.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
Surprisingly, hyper parameter tuning had a reverse effect on the accuracy of the model. The score increased from 0.53 to 0.55.
### If you were given more time with this dataset, where do you think you would spend more time?
I would spend more time doing some feature engineering and model optimization.
### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|default|default|default|1.8|
|add_features|default|default|default|0.53598|
|hpo|NN epochs:10,activation:[relu, softrelu, tanh], layers=[[100], [1000], [200, 100], [300, 200, 100]]|GBM num_boost_round:100, num_leaves=[26: 66]|?|0.55321|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](model_test_score.png)

## Summary
The initial model was not doing well so we made some EDA to get more insights about data. When we divided the datetime column into three columns, the accuracy increased