![](UTA-DataScience-Logo.png)

# PCOS Diagnosis Machine Learning

* This repository holds an attempt to apply a KNN Classifier to correctly diagnose PCOS using data from the "PCOS Diagnosis Dataset" Kaggle challenge (https://www.kaggle.com/datasets/samikshadalvi/pcos-diagnosis-dataset?resource=download).

## Overview

* The task for this dataset is to utilize the five features of typical symptoms or risk factors to predict PCOS diagnosis. The approach in this repository is done as a classification task, utilizing the cleaned and scaled data as the input for the K-Nearest Neighbor Classifier model and then evaluated based on accuracy. The K-Nearest Neighbor Classifier model was able to predict PCOS diagnosis with a 97% accuracy while minimizing the amount of false positives and negatives.

## Summary of Workdone

### Data

* Type: CSV file with 4 quantitative variables, 1 categorical variable, and the target variable of PCOS diagnosis
* Size: 1000 rows and 6 features
* Instances (Train, Test, Validation Split): 600 patients for training, 200 for testing, 200 for validation

#### Preprocessing / Clean up

* No missing values or duplicates were detected
* All categorical variables were already encoded
* The only change done was scaling all of the features using the StandardScaler

#### Data Visualization
![pcosfeatures](https://github.com/user-attachments/assets/a23054ca-0896-43aa-8280-6e839e6165a9)
![menstrualtable](https://github.com/user-attachments/assets/6808104c-87c9-438f-aa5c-d32df8cacf5c)
![pcostable](https://github.com/user-attachments/assets/72f125e1-a649-40d1-8953-e1e262adc627)
![pcoshistogram](https://github.com/user-attachments/assets/a4dc1345-d638-4de9-81f6-d7d9be778f4b)
From the visualizations, we can observe a few things:
* Based on the histograms, all of the features are fairly uniform without any skewing
* The menstrual irregularity feature seems to be fairly balanced
* There's a potential issue with an imbalance between the classes in the PCOS diagnosis feature
* Based on the boxplots, it appears that there aren't any outliers in any of the features

### Problem Formulation

* Input: 5 features of patient symptoms/risk factors (both quantitative and categorical)
* Output: PCOS Diagnosis (binary)

Models:

* K-Nearest Neighbor Classifier- chosen due to its simplicity that works well with the dataset and its ability to make predictions based on similarities between data points.

Hyperparameters:

* Number of k neighbors considered for classification

### Training

Environment:
* Python (Both Jupyter Notebook and Google Collab)
* Libraries Used: pandas, numpy, matplotlib, seaborn, scikit-learn

Training Time:
* Very short due to size of dataset and simplicity of the model (a few seconds)

Stopping Training:
* Training was very quick, so there was no need to intentionally stop it

Difficulties:
* The effectiveness of the KNN model is derived from the distance between data points; so without scaling, the model performs very poorly on the dataset. This was solved by ensuring all features were scaled properly before training the model.

### Performance Comparison

* Metric: Accuracy and Confusion Matrix (low number of false positives and false negatives)
* Visualizations:

![pcosconfusionmatrix](https://github.com/user-attachments/assets/86162bfa-5186-474e-a10b-a4b397612e56)

* Accuracy: 0.97 after cleaning and scaling
* Confusion Matrix: Only 2 False Negatives and 4 False Positives (very low when compared to the 200 patient group)

### Conclusions

* The cleaned dataset enabled the KNN Classifier model to work smoothly without many changes needed.
* Overall, the KNN Classifier Model performed well with a 97% accuracy in predicting PCOS diagnosis and minimal false negatives and false positives.

### Future Work

* Find a larger and more diverse dataset to increase the practicality of the model (the dataset was already cleaned and it only had 1000 patients with 199 being positive for the condition).
* Try to find a dataset with other features like Type 2 Diabetes Diagnosis and Family History since these features are said to have an effect on PCOS diagnosis.
* Investigate other simple models that could be applied without overfitting to the dataset.

## How to reproduce results

To fully reproduce the results from this repository, the steps below can be followed using a locally ran notebook or a cloud-based environment.
1. Boot up whatever software will be used to code (Ex: Jupyter Notebook or Google Collab(recommended))
2. Import the relevant libraries/packages (Ex: pandas, numpy, matplotlib, seaborn, scikit-learn)
3. Load the pcos_dataset.csv into the notebook as a dataframe
4. Apply the StandardScaler to all features except for the target variable
5. Properly declare both the features and target variable then split the data into training, testing, and validation sets
6. Import and define the KNN Classifier model
7. Fit the model to the training sets
8. Make predictions on the validation set using the model and compare with the actual results
9. Extract the accuracy score and generate a confusion matrix to ensure the model worked

### Overview of files in repository

* DATA3402_Final_Project_PCOS.ipynb: The final machine learning code including all relevant analysis, scaling, model training, and results.

### Software Setup

Required Packages/Libraries:
* pandas as pd
* numpy as np
* matplotlib.pyplot as plt
* seaborn as sns
* StandardScaler from sklearn.preprocessing
* KNeighborsClassifier from sklearn.neighbors
* train_test_split from sklearn.model_selection
* accuracy_score from sklearn.metrics
* confusion_matrix, ConfusionMatrixDisplay from sklearn.metrics

### Data

* Found on Kaggle.com titled "PCOS Diagnosis Dataset"
* Can be downloaded directly from the website as CSV file
* Once downloaded, it can be uploaded to the local directory then loaded as a dataframe
* If not, it can be imported into the notebook via kagglehub

### Training

* Properly define the features and target variable
* Split the dataset into training, testing, and validation sets
* After importing the desired machine learning model, fit it to the training sets
* After fitting, run predictions based on the testing and validation sets then compare with the actual results
* Extract the desired metrics to determine the effectiveness of the model

#### Performance Evaluation

* To properly evaluate performance, it depends on the metrics used
* In this repository, the metrics used are accuracy and an evaluation of a confusion matrix
* The extracted accuracy should be as close to 1 as possible to be considered an effective model
  * The accuracy shouldn't be too perfect either to avoid a model overfitting and memorizing the dataset
* The confusion matrix should have values as close to 0 as possible in any box where there's a 0 and 1 intersection between the predicted and the actual


## Citations

* Dataset from Kaggle: https://www.kaggle.com/datasets/samikshadalvi/pcos-diagnosis-dataset?resource=download







