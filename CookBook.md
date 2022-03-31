<h3 id="the-run_analysisr-script-performs-the-data-preparation-and-then-followed-by-the-5-steps-required-as-described-in-the-course-projects-definition">The run_analysis.R script performs the data preparation and then followed by the 5 steps required as described in the course project’s definition.</h3>
<h2 id="download-the-dataset">Download the dataset</h2>
<p><em>Dataset downloaded and extracted under the folder called UCI HAR Dataset</em></p>
<p>Assign each data to variables</p>
<ul>
<li>features &lt;- features.txt : 561 rows, 2 columns<ul>
<li>The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.</li>
</ul>
</li>
<li>activities &lt;- activity_labels.txt : 6 rows, 2 columns<ul>
<li>List of activities performed when the corresponding measurements were taken and its codes (labels)</li>
</ul>
</li>
<li>subject_test &lt;- test/subject_test.txt : 2947 rows, 1 column<ul>
<li>contains test data of 9/30 volunteer test subjects being observed</li>
</ul>
</li>
<li>x_test &lt;- test/X_test.txt : 2947 rows, 561 columns<ul>
<li>contains recorded features test data</li>
</ul>
</li>
<li>y_test &lt;- test/y_test.txt : 2947 rows, 1 columns<ul>
<li>contains test data of activities’code labels</li>
</ul>
</li>
<li>subject_train &lt;- test/subject_train.txt : 7352 rows, 1 column<h3 id="contains-train-data-of-2130-volunteer-subjects-being-observed">contains train data of 21/30 volunteer subjects being observed</h3>
</li>
<li>x_train &lt;- test/X_train.txt : 7352 rows, 561 columns<ul>
<li>contains recorded features train data</li>
</ul>
</li>
<li>y_train &lt;- test/y_train.txt : 7352 rows, 1 columns<ul>
<li>contains train data of activities’code labels</li>
</ul>
</li>
</ul>
<h2 id="merges-the-training-and-the-test-sets-to-create-one-data-set">Merges the training and the test sets to create one data set</h2>
<h3 id="x-10299-rows-561-columns-is-created-by-merging--x_train-and-x_test-using-rbind-function">X (10299 rows, 561 columns) is created by merging  x_train and x_test using rbind() function</h3>
<h2 id="y-10299-rows-1-column-is-created-by-merging-y_train-and-y_test-using-rbind-function">Y (10299 rows, 1 column) is created by merging y_train and y_test using rbind() function</h2>
<h2 id="subject-10299-rows-1-column-is-created-by-merging-subject_train-and-subject_test-using-rbind-function">Subject (10299 rows, 1 column) is created by merging subject_train and subject_test using rbind() function</h2>
<h2 id="merged_data-10299-rows-563-column-is-created-by-merging-subject-y-and-x-using-cbind-function">Merged_Data (10299 rows, 563 column) is created by merging Subject, Y and X using cbind() function</h2>
<h2 id="extracts-only-the-measurements-on-the-mean-and-standard-deviation-for-each-measurement">Extracts only the measurements on the mean and standard deviation for each measurement</h2>
<ul>
<li><p>TidyData (10299 rows, 88 columns) is created by subsetting Merged_Data, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement</p>
</li>
<li><p>Uses descriptive activity names to name the activities in the data set</p>
</li>
<li><p>Entire numbers in code column of the TidyData replaced with corresponding activity taken from second column of the activities variable</p>
</li>
</ul>
<h2 id="appropriately-labels-the-data-set-with-descriptive-variable-names">Appropriately labels the data set with descriptive variable names</h2>
<h3 id="code-column-in-tidydata-renamed-into-activities">code column in TidyData renamed into activities</h3>
<ul>
<li>All Acc in column’s name replaced by Accelerometer</li>
<li>All Gyro in column’s name replaced by Gyroscope</li>
<li>All BodyBody in column’s name replaced by Body</li>
<li>All Mag in column’s name replaced by Magnitude</li>
<li>All start with character f in column’s name replaced by Frequency</li>
<li>All start with character t in column’s name replaced by Time</li>
</ul>
<h3 id="from-the-data-set-in-step-4-creates-a-second-independent-tidy-data-set-with-the-average-of-each-variable-for-each-activity-and-each-subject">From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject</h3>
<p><em>FinalData (180 rows, 88 columns) is created by sumarizing TidyData taking the means of each variable for each activity and each subject, after groupped by subject and activity.</em></p>
<h3 id="export-finaldata-into-finaldatatxt-file">Export FinalData into FinalData.txt file.</h3>
