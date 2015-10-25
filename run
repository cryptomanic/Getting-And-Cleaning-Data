# read and load X_test.txt file
x_test <- read.table('./test/X_test.txt')
# set the column names of x_test data frame
names(x_test) <- read.table('features.txt')[,2]

# read and load y_test.txt file
y_test <- read.table('./test/y_test.txt')
# set the column names of y_test data frame
names(y_test) <- c('Activity Labels')

# read and load subject_test.txt file
s_test <- read.table('./test/subject_test.txt')
# set the column names of s_test data frame
names(s_test) <- c('Who performed the activity')

# combine s_test, y_test, x_test to obtain complete test data
test <- cbind(s_test,y_test,x_test)

# repeat the same as above to obtain complete train data

# read and load X_train.txt file
x_train <- read.table('./train/X_train.txt')
# set the column names of x_train data frame
names(x_train) <- read.table('features.txt')[,2]

# read and load y_train.txt file
y_train <- read.table('./train/y_train.txt')
# set the column names of y_train data frame
names(y_train) <- c('Activity Labels')

# read and load subject_train.txt file
s_train <- read.table('./train/subject_train.txt')
# set the column names of s_train data frame
names(s_train) <- c('Who performed the activity')

# combine s_train, y_train, x_rain to obtain complete train data
train <- cbind(s_train,y_train,x_train)

# merge test and train datasets
merged_data <- rbind(test,train)

# read and load descriptive activity file
des_labels <- read.table('activity_labels.txt')[,2]

# Uses descriptive activity names to name the activities in the data set
merged_data[,2] <- sapply(merged_data[,'Activity Labels'], function(i) des_labels[i])

# Extracts only the measurements on the mean and standard deviation for each measurement
required_col <- grepl("mean|std", names(merged_data))
required_col[1:2] <- c(TRUE,TRUE)

tidy_data <- merged_data[,required_col]
  
write.table(tidy_data,row.name=FALSE, file = "./tidy_data.txt")
