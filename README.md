![](UTA-DataScience-Logo.png)

# PCOS Diagnosis Machine Learning

* This repository holds an attempt to apply a KNN Classifier to correctly diagnose PCOS using data from the "PCOS Diagnosis Dataset" Kaggle challenge (https://www.kaggle.com/datasets/samikshadalvi/pcos-diagnosis-dataset?resource=download).

## Overview

* The task for this dataset is to utilize the five features of typical symptoms or risk factors to predict PCOS diagnosis. The approach in this repository is done as a classification task, utilizing the cleaned and scaled data as the input for the K-Nearest Neighbor Classifier model and then evaluated based on accuracy. The K-Nearest Neighbor Classifier model was able to predict PCOS diagnosis with a 97% accuracy while minimizing the amount of false positives and negatives.

## Summary of Workdone

### Data

* Data:
  * Type: CSV file with 4 quantitative variables, 1 categorical variable, and the target variable of PCOS diagnosis
  * Size: 1000 rows and 6 features
  * Instances (Train, Test, Validation Split): 600 patients for training, 200 for testing, 200 for validation

#### Preprocessing / Clean up

* No missing values or duplicates were detected
* All categorical variables were already encoded
* The only change done was scaling all of the features using the StandardScaler

#### Data Visualization
![pcosfeatures](https://github.com/user-attachments/assets/a23054ca-0896-43aa-8280-6e839e6165a9)
![pcoshistogram](https://github.com/user-attachments/assets/a4dc1345-d638-4de9-81f6-d7d9be778f4b)
From the visualizations, we can observe a few things:
* Based on the histograms, all of the features are fairly uniform without any skewing
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

* Describe the training:
  * How you trained: software and hardware.
  * How did training take.
  * Training curves (loss vs epoch for test/train).
  * How did you decide to stop training.
  * Any difficulties? How did you resolve them?

### Performance Comparison

* Clearly define the key performance metric(s).
* Show/compare results in one table.
* Show one (or few) visualization(s) of results, for example ROC curves.

### Conclusions

* State any conclusions you can infer from your work. Example: LSTM work better than GRU.

### Future Work

* What would be the next thing that you would try.
* What are some other studies that can be done starting from here.

## How to reproduce results

* In this section, provide instructions at least one of the following:
   * Reproduce your results fully, including training.
   * Apply this package to other data. For example, how to use the model you trained.
   * Use this package to perform their own study.
* Also describe what resources to use for this package, if appropirate. For example, point them to Collab and TPUs.

### Overview of files in repository

* Describe the directory structure, if any.
* List all relavent files and describe their role in the package.
* An example:
  * utils.py: various functions that are used in cleaning and visualizing data.
  * preprocess.ipynb: Takes input data in CSV and writes out data frame after cleanup.
  * visualization.ipynb: Creates various visualizations of the data.
  * models.py: Contains functions that build the various models.
  * training-model-1.ipynb: Trains the first model and saves model during training.
  * training-model-2.ipynb: Trains the second model and saves model during training.
  * training-model-3.ipynb: Trains the third model and saves model during training.
  * performance.ipynb: loads multiple trained models and compares results.
  * inference.ipynb: loads a trained model and applies it to test data to create kaggle submission.

* Note that all of these notebooks should contain enough text for someone to understand what is happening.

### Software Setup
* List all of the required packages.
* If not standard, provide or point to instruction for installing the packages.
* Describe how to install your package.

### Data

* Point to where they can download the data.
* Lead them through preprocessing steps, if necessary.

### Training

* Describe how to train the model

#### Performance Evaluation

* Describe how to run the performance evaluation.


## Citations

* Provide any references.







