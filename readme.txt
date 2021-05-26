Kaggle's machine learning from disaster challenge.

This challenge is posted on Kaggle at https://www.kaggle.com/c/titanic .
The goal of this data-science challenge is to predict the survival of
417 titanic passengers based on 891 labeled training examples.
I tackled this problem using a random forest to find the best predictor variables
and a decision tree to train the model.

The steps I used are as follows:

1. Select the strongest predictor variables using a random forest.
2. Use ensemble to train 5 different models and use ROC AUC to evaluate the performance of each model
3. Evaluate the best model with a confusion matrix

From 15 available variables I ended up using the following as the strongest:
"Age",  "Fare", "Sex_male", "Pclass", "SibSP" and "Parch".
However the "Age" variable is not available for 20 percent of the training examples.
I therefore proceeded to:

4. Train a training model for the missing age data with a Random forest regressor
5. Predict the missing age of the training examples in the train and in the test dataset

With the age data for all training and test examples in place

6. Use ensemble to train 5 different models on the now completed examples
7. Select the decision tree algorithm (based on the ROC AUC) to train on the entire dataset
8. Make prediction for the unlabelled data

The final model has a prediction accuracy of 0.78468
