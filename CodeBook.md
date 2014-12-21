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

* `Means`: Measurements on the mean for each measurement, which is required in part 1 of project.
* `Stds`: Measurements on the standard deviation for each measurement, which is required in part 1 of project. 
* `Means_Stds`: Dataset combined from `Means` and `Stds`.

* `activity_idnames`: The descriptive activity names required in part 3 of project.


* `features_names`: The descriptive variable names required in part 4 of project.

* `tidydata`: tidy data required in final part of this project. 

More information about the files is available in `README.txt`. More information about the features is available in `features_info.txt`.

### Data files that were not used

This analysis was performed using only the files above, and did not use the raw signal data. Therefore, the data files in the "Inertial Signals" folders were ignored.

### Processing steps

1. All of the relevant data files were read into data frames, appropriate column headers were added, and the training and test sets were combined into a single data set.
2. All feature columns were removed that did not contain the exact string "mean()" or "std()". This left 66 feature columns, plus the subjectID and activity columns.
3. The activity column was converted from a integer to a factor, using labels describing the activities.
4. A tidy data set was created containing the mean of each feature for each subject and each activity. Thus, subject #1 has 6 rows in the tidy data set (one row for each activity), and each row contains the mean value for each of the 66 features for that subject/activity combination. Since there are 30 subjects, there are a total of 180 rows.
5. The tidy data set was output to a CSV file.
