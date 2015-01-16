# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data
First lets read data from file "activity.zip" and store it in dataframe named "activity":

```r
activity <- read.csv(unz("activity.zip", "activity.csv"))
```

Lets look at the head of the data:

```r
head(activity)
```

```
##   steps       date interval
## 1    NA 2012-10-01        0
## 2    NA 2012-10-01        5
## 3    NA 2012-10-01       10
## 4    NA 2012-10-01       15
## 5    NA 2012-10-01       20
## 6    NA 2012-10-01       25
```

The data is in narrow form and it is OK for further analisys. We can admit that there are NA values in it.


## What is mean total number of steps taken per day?
For this part of assignment we will ignore the missing values in the dataset.
We will use dplyr package so lets load it. Be sure to install it first with `install.packages("dplyr")` if you do not have it already.

```r
library(dplyr)
```

Lets make a histogram of the total number of steps taken each day:

```r
activityByDate <- group_by(activity, date) %>% summarise(steps = sum(steps))
barplot(activityByDate$steps)
```

![](PA1_template_files/figure-html/unnamed-chunk-4-1.png) 

Then lets calculate the mean and median total number of steps taken per day:

```r
mean(activityByDate$steps, na.rm = TRUE)
```

```
## [1] 10766.19
```

```r
median(activityByDate$steps, na.rm = TRUE)
```

```
## [1] 10765
```
## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
