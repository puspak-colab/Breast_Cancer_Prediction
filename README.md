# Breast_Cancer_Prediction:
This dataset has been downloaded from UCI Machine Learning repository: *https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29*. 
It consists of 33 features and 569 entries. This dataset particularly describes different features of 569 patients diagnosed for Breast Tumour either it be **Malignant** or **Benign**. Here a model should be trained on the data which predicts a Tumour be Malignant or Benign. *In this case, different machine learning algorithms are used and their respective accuracy scores are being checked.*
First of all, the ***first column*** and the ***last column*** be deleted as they carry no significant meaning for analysis and model training. 
The second column of the dataset consists of the end result; **M** for **Malignant** & **B** for **Benign**, so it should be considered as the *target variable*.
Having checked for the null values (There is none in the dataset), numbers of **M**s & **B**s are counted in the second column and plotting them with the help of Seaborn library’s Countplot. After that, the Correlation matrix be formed & subsequent Heatmap being plotted. There are some negative correlation values can be observed by the Heatmap, and some of them are being plotted in Scatter plots. 
Now the Independent features or Predictors be separated and saved in “X” and the Target variable be saved as “y”. As the target variable contains only two categories it must be encoded to convert it into integers i.e., *0s and 1s for Bs and Ms respectively*. After that, the whole data set be divided between training and test sets *(test set size be 35% of the total dataset)* with four distinct variables **X_train**, **X_test**, **y_train** & **y_test**. Now, the predictors should be normalized to get them into specific range, for that *scikitlearn’s **‘StandardScalar()’*** being used. 
Now some of the machine learning algorithms be used to train the model on the training data and test its performances on test set. After getting the respective accuracy scores for each of the algorithms and perform K-fold cross validation where, *K=10*; to check *whether the previous accuracy score is just a matter of good luck or the model trained really well*.
After that, the **AUC** scores for all the algorithms been calculated. Finally, **AIC** scores being calculated for two highest ROC-AUC score-holders. 

## K-fold Cross Validation: 
*Cross-validation is a resampling procedure used to evaluate machine learning models on a limited data sample.
The procedure has a single parameter called k that refers to the number of groups that a given data sample is to be split into. As such, the procedure is often called k-fold cross-validation. When a specific value for k is chosen, it may be used in place of k in the reference to the model, such as k=10 becoming 10-fold cross-validation.
Cross-validation is primarily used in applied machine learning to estimate the skill of a machine learning model on unseen data. That is, to use a limited sample in order to estimate how the model is expected to perform in general when used to make predictions on data not used during the training of the model.
It is a popular method because it is simple to understand and because it generally results in a less biased or less optimistic estimate of the model skill than other methods, such as a simple train/test split.*

## AUC Score:
*AUC stands for **“Area Under the ROC Curve”** which plots **TPR (True Positive Rate)** against the **FPR (False Positive Rate)** where TPR is on the y-axis and FPR is on the x-axis.
AUC - ROC curve is a performance measurement for the classification problems at various threshold settings. ROC is a probability curve and AUC represents the degree or measure of separability. It tells how much the model is capable of distinguishing between classes. Higher the AUC, the better the model is at predicting 0 classes as 0 and 1 classes as 1. By analogy, the Higher the AUC, the better the model.*

## AIC:
*The **Akaike information criterion (AIC)** is a mathematical method for evaluating how well a model fits the data it was generated from. In statistics, AIC is used to compare different possible models and determine which one is the best fit for the data. AIC is calculated from:
•	the number of independent variables used to build the model.
•	the maximum likelihood estimate of the model (how well the model reproduces the data).
The best-fit model according to AIC is the one that explains the greatest amount of variation using the fewest possible independent variables.
To compare models using AIC, you need to calculate the AIC of each model. If a model is more than 2 AIC units lower than another, then it is considered significantly better than that model.*
