# breast_cancer_classification

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Breast cancer is one of a dangerous disease in the world. In my country, Indonesia there are more than 150 thousand cases per year. Therefore we need to predict is the breast cancer determine as benign or malignant to help doctor to give more efficient solution to patient. In this case we will use machine learning model to predict is the breast cancer benign or malignant ?.

# Dataset

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;For the dataset, I used [Breast Cancer Wisconsin (Diagnostic) Data Set - Kaggle](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data) 

![image](https://user-images.githubusercontent.com/91602612/214741835-4052a2c9-88da-4594-b6c1-09271b3be9e7.png)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This dataset contains 33 features and 569 records, and you can see the detail information from that link about the dataset.

# Exploratory Data Analysis

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In this step I need to explore more about the dataset, therefore I know more about the dataset. this is the steps that I have done:

1. I am looking the information of the dataset about what is the data type for each of features, how much the features we had, and how much records that we had,
2. I am checking the statistical information about the features that contains numerical values,
3. I am checking about the null or missing values in the dataset, missing values can be an important thing that we must handle because it can impact to our model's peformacne, fortunately that this dataset has no missing values,
4. Then I check the label to see if I have an imbalance dataset, and I used barplot to visualize total of each label,
5. I encode the label because I want to see the correlation of each features to the label, and I used **hot map** to plot the correlation for all features,
6. Then I drop features that has weak correlationt to the label

# Data Preprocessing

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In this step I will process the dataset therefore I can use the dataset to build a model, the following steps I used for prepocessing my dataset:

1. First step I define x and y variable to define independent data (x) and dependent data (y /label). I drop **diagnosis column** because it is a dependent data and I only used **diagnosis column** for my dependent variable,
2. I am using standard scaler to normalize the independent data (variable x) because each columns has different scale, I normalize them therefore all the columns value has value between 0 to 1 so they have same scale.
3. Then I split the dataset into x_train, x_test, y_train, and y_test with random state = 42, and test size = 30% and train size = 70%.

# Modeling 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In this step I started to built 2 model for my machine learning model to predict which the patient has a malignant or benign breast cancer.

## XGBOOST

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;First model I used XGBOOST Classifier, XGBOOST is a model that implemantation of gradient boosted decision trees, you can see the detail implementation from this link [XGBOOST](https://www.geeksforgeeks.org/xgboost/), and you can also see the documentation in this link {XGBOOST Documentation}(https://xgboost.readthedocs.io/en/stable/python/python_api.html). From XGBOOST Classifier I got 98% with n_estimators = 200 as my parameter.

![image](https://user-images.githubusercontent.com/91602612/215121047-1e237723-f6f8-449f-a0a8-806255e8f7ab.png) ![image](https://user-images.githubusercontent.com/91602612/215121101-f4810ab4-c7d2-42a4-a0da-c54ac347239e.png)

## TABFPN

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Second model I used TABFPN model, this model I found from [TABFPN](https://arxiv.org/abs/2207.01848), I used this model because from the title of the article it says that this model can solves a small classification model in a second, and after I tested it, it gave me a second to training the dataset and also gave me a good accuracy. The accuracy in this model also 98% same as XGBOOST but with different time to train the model.

![image](https://user-images.githubusercontent.com/91602612/215122085-217db8a0-8f28-450d-879a-f87c927b5624.png) ![image](https://user-images.githubusercontent.com/91602612/215122117-dbe685fe-8270-4bd7-b0c7-febe99fd3c46.png)



