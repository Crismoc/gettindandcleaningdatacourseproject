# README

## Original data comes from "Human Activity Recognition Using Smartphones Data Set". In order to run the script in the repo you have to dowload this data.
http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

#Steps

## 1 Loading data #

In this step is important that you set the right working directories where the objects are.

### 1.1 Features names

Load the "features.txt" that will be used to name the 561 data measurents.

### 1.2 Test data

Given that the complete data comes divided into 2 groups (test and train) it is necessary to load both. Here we load into R objects "X_test.txt" (data froma the 561 measurements), "Y_test.txt" (activity identificator for the 6 activities recorded) and "subject_test" (subject identificator for the 30 participants in the study). With read.table we use col.names argument to name with the column of feature the measurements. There are 2947 observations in this dataset.

### 1.3 Train data

The same as the last step, but for the train data. There are 7352 observations in this dataset.

## 2 Merging

In this step the columns of activities and subjects are added to train and test data. Then the complete data is created.

### 2.1 Adding subject id column to train and test data

The columns of subject are added to test and train data.

### 2.2 Adding activity column

The columns of activity are added to test and train data.

### 2.3 Merging test and train data

Train and test data (with activity and subject columns) are merged. A dataset of 10299 observations is obtained.

## 3 Extracting columns with mean or std of measurements

Here we find the columns wich have "mean" or "std" in order to subset the measurements of mean and standard deviation.

### 3.1 Finding columns with mean or std in its name

This is done by searching with grep into the features column with measurements variable names. Then a vector with the position is created.

### 3.2 Creating a data set with variables "subject", "activity" and those with mean and std in its name

A subset of the completedata is created with the vector with mean and std positions plus "activity" and "subject" columns. This subset has 10299 observations of 81 variables.

### 3.3 Recoding activity number id into activity name

The value of the activities is recoded with the activity name.

### 3.4 Labeling with friendly descriptive variable names

For having a tidy dataset the variable names are edited with no dots inbetween and just with capital letters at the beggining of word for readability.

## 4 Creating a tidy dataset with the averages of mean and std measurements by subject and activity

A tidy dataset with the average of mean and standard deviation measurements for each subject and activity is created with aggregate. Since there are 6 activities and 30 subjects, a 180 observations by 81 measurements is obtained.

## 5 Exporting data set #

The tidy dataset is exported as a .txt file. Is important to set the desired working directory where you want to find the file.