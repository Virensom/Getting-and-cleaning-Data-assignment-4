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

List of the tidydata variables

[1] "activity"                                           "Angle.TimeBodyAccelerometerJerkMean..GravityMean." 
 [3] "Angle.TimeBodyAccelerometerMean.Gravity."           "Angle.TimeBodyGyroscopeJerkMean.GravityMean."      
 [5] "Angle.TimeBodyGyroscopeMean.GravityMean."           "Angle.X.GravityMean."                              
 [7] "Angle.Y.GravityMean."                               "Angle.Z.GravityMean."                              
 [9] "FrequencyBodyAccelerometer.mean...X"                "FrequencyBodyAccelerometer.mean...Y"               
[11] "FrequencyBodyAccelerometer.mean...Z"                "FrequencyBodyAccelerometer.meanFreq...X"           
[13] "FrequencyBodyAccelerometer.meanFreq...Y"            "FrequencyBodyAccelerometer.meanFreq...Z"           
[15] "FrequencyBodyAccelerometer.std...X"                 "FrequencyBodyAccelerometer.std...Y"                
[17] "FrequencyBodyAccelerometer.std...Z"                 "FrequencyBodyAccelerometerJerk.mean...X"           
[19] "FrequencyBodyAccelerometerJerk.mean...Y"            "FrequencyBodyAccelerometerJerk.mean...Z"           
[21] "FrequencyBodyAccelerometerJerk.meanFreq...X"        "FrequencyBodyAccelerometerJerk.meanFreq...Y"       
[23] "FrequencyBodyAccelerometerJerk.meanFreq...Z"        "FrequencyBodyAccelerometerJerk.std...X"            
[25] "FrequencyBodyAccelerometerJerk.std...Y"             "FrequencyBodyAccelerometerJerk.std...Z"            
[27] "FrequencyBodyAccelerometerJerkMagnitude.mean.."     "FrequencyBodyAccelerometerJerkMagnitude.meanFreq.."
[29] "FrequencyBodyAccelerometerJerkMagnitude.std.."      "FrequencyBodyAccelerometerMagnitude.mean.."        
[31] "FrequencyBodyAccelerometerMagnitude.meanFreq.."     "FrequencyBodyAccelerometerMagnitude.std.."         
[33] "FrequencyBodyGyroscope.mean...X"                    "FrequencyBodyGyroscope.mean...Y"                   
[35] "FrequencyBodyGyroscope.mean...Z"                    "FrequencyBodyGyroscope.meanFreq...X"               
[37] "FrequencyBodyGyroscope.meanFreq...Y"                "FrequencyBodyGyroscope.meanFreq...Z"               
[39] "FrequencyBodyGyroscope.std...X"                     "FrequencyBodyGyroscope.std...Y"                    
[41] "FrequencyBodyGyroscope.std...Z"                     "FrequencyBodyGyroscopeJerkMagnitude.mean.."        
[43] "FrequencyBodyGyroscopeJerkMagnitude.meanFreq.."     "FrequencyBodyGyroscopeJerkMagnitude.std.."         
[45] "FrequencyBodyGyroscopeMagnitude.mean.."             "FrequencyBodyGyroscopeMagnitude.meanFreq.."        
[47] "FrequencyBodyGyroscopeMagnitude.std.."              "subject"                                           
[49] "TimeBodyAccelerometer.mean...X"                     "TimeBodyAccelerometer.mean...Y"                    
[51] "TimeBodyAccelerometer.mean...Z"                     "TimeBodyAccelerometer.std...X"                     
[53] "TimeBodyAccelerometer.std...Y"                      "TimeBodyAccelerometer.std...Z"                     
[55] "TimeBodyAccelerometerJerk.mean...X"                 "TimeBodyAccelerometerJerk.mean...Y"                
[57] "TimeBodyAccelerometerJerk.mean...Z"                 "TimeBodyAccelerometerJerk.std...X"                 
[59] "TimeBodyAccelerometerJerk.std...Y"                  "TimeBodyAccelerometerJerk.std...Z"                 
[61] "TimeBodyAccelerometerJerkMagnitude.mean.."          "TimeBodyAccelerometerJerkMagnitude.std.."          
[63] "TimeBodyAccelerometerMagnitude.mean.."              "TimeBodyAccelerometerMagnitude.std.."              
[65] "TimeBodyGyroscope.mean...X"                         "TimeBodyGyroscope.mean...Y"                        
[67] "TimeBodyGyroscope.mean...Z"                         "TimeBodyGyroscope.std...X"                         
[69] "TimeBodyGyroscope.std...Y"                          "TimeBodyGyroscope.std...Z"                         
[71] "TimeBodyGyroscopeJerk.mean...X"                     "TimeBodyGyroscopeJerk.mean...Y"                    
[73] "TimeBodyGyroscopeJerk.mean...Z"                     "TimeBodyGyroscopeJerk.std...X"                     
[75] "TimeBodyGyroscopeJerk.std...Y"                      "TimeBodyGyroscopeJerk.std...Z"                     
[77] "TimeBodyGyroscopeJerkMagnitude.mean.."              "TimeBodyGyroscopeJerkMagnitude.std.."              
[79] "TimeBodyGyroscopeMagnitude.mean.."                  "TimeBodyGyroscopeMagnitude.std.."                  
[81] "TimeGravityAccelerometer.mean...X"                  "TimeGravityAccelerometer.mean...Y"                 
[83] "TimeGravityAccelerometer.mean...Z"                  "TimeGravityAccelerometer.std...X"                  
[85] "TimeGravityAccelerometer.std...Y"                   "TimeGravityAccelerometer.std...Z"                  
[87] "TimeGravityAccelerometerMagnitude.mean.."           "TimeGravityAccelerometerMagnitude.std.."     

From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
AverageData (180 rows, 88 columns) is created by sumarizing TidyData taking the means of each variable for each activity and each subject, after groupped by subject and activity.
Export AverageData into AverageData.txt file.