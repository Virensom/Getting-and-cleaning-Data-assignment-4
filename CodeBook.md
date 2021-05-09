---
title: "CodeBook"
output: html_notebook
---

This is for Getting and Cleaning data assignment


Download the dataset
The Dataset is downloaded for the specified source and extracted under the folder called UCI HAR Dataset

Created a variable for each data set
```{r}
features refers to features.txt
activities refers activity_labels.txt
subject_test refers subject_test.txt
x_test refers X_test.txt
y_test refers y_test.txt
subject_train refers subject_train.txt
x_train refers X_train.txt
y_train refers y_train.txt
```
Merges the training and the test sets to create one data set

X (10299 rows, 561 columns) is created by merging x_train and x_test using rbind() function
Y (10299 rows, 1 column) is created by merging y_train and y_test using rbind() function
Subject (10299 rows, 1 column) is created by merging subject_train and subject_test using rbind() function
Merged_Data (10299 rows, 563 column) is created by merging Subject, Y and X using cbind() function



Extracts only the measurements on the mean and standard deviation for each measurement
TidyData (10299 rows, 88 columns) is created by subsetting Merged_Data, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement

Uses descriptive activity names to name the activities in the data set
Entire numbers in code column of the TidyData replaced with corresponding activity taken from second column of the activities variable

Appropriately labels the data set with descriptive variable names
code column in TidyData renamed into activities
All Acc in column’s name replaced by Accelerometer
All Gyro in column’s name replaced by Gyroscope
All BodyBody in column’s name replaced by Body
All Mag in column’s name replaced by Magnitude
All start with character f in column’s name replaced by Frequency
All start with character t in column’s name replaced by Time

From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
AverageData (180 rows, 88 columns) is created by sumarizing TidyData taking the means of each variable for each activity and each subject, after groupped by subject and activity.
Export AverageData into AverageData.txt file.