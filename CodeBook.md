## Code Book

This code book will describe the data, varialbes used in this project, as well as the processing performed to create the resulting tidy data set.

### Overview

30 volunteers performed 6 different activities while wearing a smartphone. The smartphone captured various data about their movements.

### Explanation of each variables

* `features`: Names of the 561 features.

* `train_y`: IDs for each of the 6 activities, 1:6, for training dataset. The mapped names are WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING. 
* `train_subject`: IDs of 30 volunteers performed 6 different activities in training dataset.
* `train_x`: The observations of measurements on 561 features, which are performed by 30 volunteers, in training dataset. 

* `test_y`: IDs for each of the 6 activities, 1:6, for test dataset. The mapped names are WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING. 
* `test_subject`: IDs of 30 volunteers performed 6 different activities in test dataset.
* `test_x`: The observations of measurements on 561 features, which are performed by 30 volunteers, in test dataset. 

* `totdata`: Mergeed dataset of the training and the test sets, which is required in part 1 of project.
* `measurement_id`: The organized IDs for 9 types of measurments related to body, gyro and total, which is creaded by customed file named `measurement_id.R`.

* `Means`: Measurements on the mean for each measurement, which is required in part 2 of project.
* `Stds`: Measurements on the standard deviation for each measurement, which is required in part 2 of project. 
* `Means_Stds`: Dataset combined from `Means` and `Stds`.

* `activity_idnames`: The descriptive activity names required in part 3 of project.

* `features_names`: The descriptive variable names required in part 4 of project.

* `tidydata`: tidy data required in final part of this project. 

More information about the files is available in `README.txt`. More information about the features is available in `features_info.txt`.

### Data files that were not used

This analysis was performed using only the files above, and did not use the raw signal data. Therefore, the data files in the "Inertial Signals" folders were ignored.

### Processing steps

1. All of the relevant data files were read into data frames, appropriate column headers were added, and the training and test sets were combined into a single data set called `totdata`.

2. Remove the parentheses in columns related to mean and standard deviation. Extract columns which are "mean" or "std". This left (53+33)=86 feature columns, plus the subjectID and activity columns.

3. Convert activities from a integer to a factor, using labels describing the activities.

4. Reforme the names of dataset retrieved in part 3, and name these names descriptively.

5. Get tidy data, and export it to a txt file.
