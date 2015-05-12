# Reproducible Research: Peer Assessment 1

## Global Settings


```
## Warning: package 'knitr' was built under R version 3.1.3
```

```
## Warning: package 'ggplot2' was built under R version 3.1.3
```

## Loading and preprocessing the data
1. Download data if it is not downloaded


2. Unzip CSV if it is not unzip yet


3. Load CSV data into variable & transform the date


## What is mean total number of steps taken per day?

1. Calculate the total number of steps taken per day

```r
totalSum <- aggregate(steps ~ date, data, sum)
head(totalSum)
```

```
##         date steps
## 1 2012-10-02   126
## 2 2012-10-03 11352
## 3 2012-10-04 12116
## 4 2012-10-05 13294
## 5 2012-10-06 15420
## 6 2012-10-07 11015
```

2. Make a histogram of the total number of steps taken each day
![](PA1_template_files/figure-html/unnamed-chunk-2-1.png) 

3. Calculate and report the mean and median of the total number of steps taken per day

- Mean is 1.0766189\times 10^{4}.
- Median is 10765.

## What is the average daily activity pattern?

1. Make a time series plot (i.e. type = "l") of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all days (y-axis)
![](PA1_template_files/figure-html/unnamed-chunk-4-1.png) 

2. Which 5-minute interval, on average across all the days in the dataset, contains the maximum number of steps?

```
##     interval    steps
## 104      835 206.1698
```

## Inputing missing values

1. Calculate and report the total number of missing values in the dataset (i.e. the total number of rows with NAs)

```
## [1] 2304
```
2. Devise a strategy for filling in all of the missing values in the dataset. The strategy does not need to be sophisticated. For example, you could use the mean/median for that day, or the mean for that 5-minute interval, etc.

- I propose to use mean of 5-minute interval to populate the missing values.

3. Create a new dataset that is equal to the original dataset but with the missing data filled in.


4.1 Make a histogram of the total number of steps taken each day and Calculate and report the mean and median total number of steps taken per day.
![](PA1_template_files/figure-html/unnamed-chunk-8-1.png) 

4.2 Do these values differ from the estimates from the first part of the assignment?

* Mean is 1.0766189\times 10^{4}. 
* Mean(Filled) is 1.0766189\times 10^{4}.
    + This is same for mean.

* Median is 10765. 
* Median is 1.0766189\times 10^{4}.
    + Yes there is minor differences since more mean data has been populated which move the median towards mean.

4.3 What is the impact of imputing missing data on the estimates of the total daily number of steps?
- Depends on the value being populated to fill the NAs, mean and median maybe tweak slightly.

## Are there differences in activity patterns between weekdays and weekends?
1. Create a new factor variable in the dataset with two levels - "weekday" and "weekend" indicating whether a given date is a weekday or weekend day.


2. Make a panel plot containing a time series plot (i.e. type = "l") of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all weekday days or weekend days (y-axis). See the README file in the GitHub repository to see an example of what this plot should look like using simulated data.

