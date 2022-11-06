# problem_tz
#problem set for day2
# load iris

df <- iris

# datafile summary 
summary(df)

# mean 
pop_mean<-mean(df$Sepal.Length)

data1<-df[sample(1:nrow(df),30),] #select 30 sample from total observation

sample_mean<-mean(data1$Sepal.Length)

# it was very similar between pop_mean and sample mean.but it we re-run sample again, sample mean are changing.

library(tidyverse)
hist(data1$Sepal.Length)

# Histogram looks like bell-shape (normal curve)
##sample 10, repeat 100
mean_list_1<-replicate(n = 100, expr = mean(sample(1:10, replace=TRUE)))
hist(mean_list_1)
mean_clt_1<-mean(mean_list_1)

## sample 30 and repeat 200
mean_list_2<-replicate(n = 200, expr = mean(sample(1:30, replace=TRUE)))
hist(mean_list_2)
mean_clt_2<-mean(mean_list_2)

## sample 30 and repeat 200
mean_list_3<-replicate(n =1000, expr = mean(sample(1:50, replace=TRUE)))
hist(mean_list_3)
mean_clt_3<-mean(mean_list_3)


## In more and more sample, the histogram is more look like in bell-shape.

