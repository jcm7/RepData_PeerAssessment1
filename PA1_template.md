# Reproducible Research: Peer Assessment 1

fname <- unzip('activity.zip', list=TRUE)$Name[1]
unzip('activity.zip', files=fname, overwrite=TRUE)

## Loading and preprocessing the data


```r
activity.data <- read.csv(file = "activity.csv")
```


## Make a histogram of the total number of steps taken each day


```r
totalPerDay <- aggregate(activity.data[, c("steps")], by=list(activity.data$date), "sum")
names(totalPerDay) <- c("date","steps")
hist(totalPerDay$steps, xlab = "Total steps", main = "Histogram of total steps")
```

![](./PA1_template_files/figure-html/unnamed-chunk-2-1.png) 


## Calculate and report the mean and median total number of steps taken per day


```r
aggregate(activity.data[, c("steps")], by=list(activity.data$date), "mean")
```

```
##       Group.1          x
## 1  2012-10-01         NA
## 2  2012-10-02  0.4375000
## 3  2012-10-03 39.4166667
## 4  2012-10-04 42.0694444
## 5  2012-10-05 46.1597222
## 6  2012-10-06 53.5416667
## 7  2012-10-07 38.2465278
## 8  2012-10-08         NA
## 9  2012-10-09 44.4826389
## 10 2012-10-10 34.3750000
## 11 2012-10-11 35.7777778
## 12 2012-10-12 60.3541667
## 13 2012-10-13 43.1458333
## 14 2012-10-14 52.4236111
## 15 2012-10-15 35.2048611
## 16 2012-10-16 52.3750000
## 17 2012-10-17 46.7083333
## 18 2012-10-18 34.9166667
## 19 2012-10-19 41.0729167
## 20 2012-10-20 36.0937500
## 21 2012-10-21 30.6284722
## 22 2012-10-22 46.7361111
## 23 2012-10-23 30.9652778
## 24 2012-10-24 29.0104167
## 25 2012-10-25  8.6527778
## 26 2012-10-26 23.5347222
## 27 2012-10-27 35.1354167
## 28 2012-10-28 39.7847222
## 29 2012-10-29 17.4236111
## 30 2012-10-30 34.0937500
## 31 2012-10-31 53.5208333
## 32 2012-11-01         NA
## 33 2012-11-02 36.8055556
## 34 2012-11-03 36.7048611
## 35 2012-11-04         NA
## 36 2012-11-05 36.2465278
## 37 2012-11-06 28.9375000
## 38 2012-11-07 44.7326389
## 39 2012-11-08 11.1770833
## 40 2012-11-09         NA
## 41 2012-11-10         NA
## 42 2012-11-11 43.7777778
## 43 2012-11-12 37.3784722
## 44 2012-11-13 25.4722222
## 45 2012-11-14         NA
## 46 2012-11-15  0.1423611
## 47 2012-11-16 18.8923611
## 48 2012-11-17 49.7881944
## 49 2012-11-18 52.4652778
## 50 2012-11-19 30.6979167
## 51 2012-11-20 15.5277778
## 52 2012-11-21 44.3993056
## 53 2012-11-22 70.9270833
## 54 2012-11-23 73.5902778
## 55 2012-11-24 50.2708333
## 56 2012-11-25 41.0902778
## 57 2012-11-26 38.7569444
## 58 2012-11-27 47.3819444
## 59 2012-11-28 35.3576389
## 60 2012-11-29 24.4687500
## 61 2012-11-30         NA
```

```r
aggregate(activity.data[, c("steps")], by=list(activity.data$date), "median")
```

```
##       Group.1  x
## 1  2012-10-01 NA
## 2  2012-10-02  0
## 3  2012-10-03  0
## 4  2012-10-04  0
## 5  2012-10-05  0
## 6  2012-10-06  0
## 7  2012-10-07  0
## 8  2012-10-08 NA
## 9  2012-10-09  0
## 10 2012-10-10  0
## 11 2012-10-11  0
## 12 2012-10-12  0
## 13 2012-10-13  0
## 14 2012-10-14  0
## 15 2012-10-15  0
## 16 2012-10-16  0
## 17 2012-10-17  0
## 18 2012-10-18  0
## 19 2012-10-19  0
## 20 2012-10-20  0
## 21 2012-10-21  0
## 22 2012-10-22  0
## 23 2012-10-23  0
## 24 2012-10-24  0
## 25 2012-10-25  0
## 26 2012-10-26  0
## 27 2012-10-27  0
## 28 2012-10-28  0
## 29 2012-10-29  0
## 30 2012-10-30  0
## 31 2012-10-31  0
## 32 2012-11-01 NA
## 33 2012-11-02  0
## 34 2012-11-03  0
## 35 2012-11-04 NA
## 36 2012-11-05  0
## 37 2012-11-06  0
## 38 2012-11-07  0
## 39 2012-11-08  0
## 40 2012-11-09 NA
## 41 2012-11-10 NA
## 42 2012-11-11  0
## 43 2012-11-12  0
## 44 2012-11-13  0
## 45 2012-11-14 NA
## 46 2012-11-15  0
## 47 2012-11-16  0
## 48 2012-11-17  0
## 49 2012-11-18  0
## 50 2012-11-19  0
## 51 2012-11-20  0
## 52 2012-11-21  0
## 53 2012-11-22  0
## 54 2012-11-23  0
## 55 2012-11-24  0
## 56 2012-11-25  0
## 57 2012-11-26  0
## 58 2012-11-27  0
## 59 2012-11-28  0
## 60 2012-11-29  0
## 61 2012-11-30 NA
```


## Make a time series plot (i.e. type = "l") of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all days (y-axis)


```r
avgPerInterval <- aggregate(activity.data[, c("steps")], by=list(activity.data$interval), "mean", na.rm=TRUE, na.action= NULL)
colnames(avgPerInterval) <- c("interval", "mean")
plot(avgPerInterval, type = "l", xlab = "5-min interval", y="Avg num steps", main = "Avg num steps per 5-min interval")
```

![](./PA1_template_files/figure-html/unnamed-chunk-4-1.png) 


## Which 5-minute interval, on average across all the days in the dataset, contains the maximum number of steps?


```r
maxMeanPerInterval <- max(avgPerInterval$mean)
avgPerInterval[avgPerInterval$mean == maxMeanPerInterval,]$interval
```

```
## [1] 835
```


## Calculate and report the total number of missing values in the dataset (i.e. the total number of rows with NAs)


```r
totalNAs <- nrow(activity.data[is.na(activity.data$steps),])
```


## Devise a strategy for filling in all of the missing values in the dataset. 


```r
replaceNAWithMean <- function(x) replace(x, is.na(x), mean(x, na.rm = TRUE))
```


## Create a new dataset that is equal to the original dataset but with the missing data filled in.


```r
library(plyr)
activity.data2 <- ddply(activity.data, ~ interval, transform, steps = replaceNAWithMean(steps))
activity.data2 <- activity.data2[order(activity.data2$date, activity.data2$interval), ]
```


## Make a histogram of the total number of steps taken each day and Calculate and report the mean and median total number of steps taken per day. Do these values differ from the estimates from the first part of the assignment? What is the impact of imputing missing data on the estimates of the total daily number of steps?


```r
totalPerDay2 <- aggregate(activity.data2[, c("steps")], by=list(activity.data2$date), "sum")
names(totalPerDay2) <- c("date","steps")
hist(totalPerDay2$steps, xlab = "Total steps", main = "Histogram of total steps")
```

![](./PA1_template_files/figure-html/unnamed-chunk-9-1.png) 


## Create a new factor variable in the dataset with two levels – “weekday” and “weekend” indicating whether a given date is a weekday or weekend day.


```r
activity.data2$date <- as.Date(activity.data2$date)
isWeekend <- (weekdays(activity.data2$date) == 'Sunday' | weekdays(activity.data2$date) == 'Saturday')
activity.data2$dayType = factor(isWeekend, labels=c("weekend",  "weekday"))
```


## Make a panel plot containing a time series plot (i.e. type = "l") of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all weekday days or weekend days (y-axis).


```r
meanPerInterval <- aggregate(activity.data2[, c("steps")], by=list(activity.data2$interval, activity.data2$dayType), "mean")
names(meanPerInterval) <- c("interval", "dayType", "steps")
library(lattice)
xyplot(steps~interval|dayType, meanPerInterval, type="l", xlab = "interval", ylab = "Number of steps", layout=(c(1,2)))
```

![](./PA1_template_files/figure-html/unnamed-chunk-11-1.png) 
