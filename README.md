# Getting-and-cleaning-Data-assignment-4
Getting and cleaning Data assignment 4

This readme file covers the explanation of how the data was transformed into a tidy set as well as what is included in the repository.

#Contents

This repository consists of 4 files

CodeBook.md : This markdown document indicating all the variables of the tidy data set.
README.md : This markdown document explaining the step by step data transformation.
run_analysis.R : This R script containing the code to transform the tidy data set.
TidyDataSet.txt : An output from the R script.


#Running the R script

To run the R script one must have the following files in their working directory
This was downloaded from the given source and extracted from the zip file.

/train/X_train.txt
/test/X_test.txt
features.txt
/test/y_test.txt
/train/y_train.txt
/test/subject_test.txt
/train/subject_train.txt

dplyr package must be installed

Once you have the unzipped folder as the working directory you can run the given R script which will create a tidy data set in a file named TidyDataSet.txt

#Step-wise Transformation

Step 1
The train and test data sets are loaded in separate dataframes.
The training and test data sets are then merged into one data set

Step 2
The next step was to extract the only the mean and standard deviation info.

Step 3
Descriptive activity names are then assigned

Step 4
Assign descriptive labels to the variable names

Step 5
From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

Step 6
Write out the data to TidyDataSet.txt in the working directory.
