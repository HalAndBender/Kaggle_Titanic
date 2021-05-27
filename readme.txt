Kaggle's machine learning from disaster challenge.

This challenge is posted on Kaggle at https://www.kaggle.com/c/titanic .
The goal of this data-science challenge is to predict the survival of
417 titanic passengers based on 891 labeled training examples.
I tackled this problem using a random forest to find the best predictor variables
and a decision tree to train the model.

Sorry about the poor descriptions of the individual steps in the Jupyter notebook. 
This was my first attempt ever to solve a ML problem. 
Here I list the steps that I roughly took to solve the problem:

1. Selected the strongest predictor variables using a random forest.
2. Used ensemble to train 5 different models and use ROC AUC to evaluate the performance of each model
3. Evaluated the best model with a confusion matrix

From 15 available variables I picked the 6 the strongest:
"Age",  "Fare", "Sex_male", "Pclass", "SibSP" and "Parch".
"Age" was by far the one with the highest predictive power. 
However the "Age" variable is not available for about 20 percent of the training examples.
I therefore proceeded to:

4. Train a model for the missing age data with a Random Forest Regressor algorithm.
5. Predict the missing age of the training examples in the train and in the test dataset.

With the completed age data I continued to

6. Use ensemble to train 5 different models 
7. Based on the outcome of the ROC AUC: select the Decision Tree algorithm to train on the entire dataset.
8. Make prediction for the unlabelled data

The final model has a prediction accuracy of 0.78468

