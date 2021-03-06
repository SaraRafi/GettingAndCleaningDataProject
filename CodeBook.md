---
title: "codebook"
author: "Sara Rafi"
date: "Sunday, December 21, 2014"
output: html_document
---


##Raw Data:
The raw data contained triaxial data for 30 subjects and 6 activities. There were a total of 561 time and frequency domain varaiables. The subjects who carried out the experiment were randomly grouped in  the two categories: test and train. The number of subjects in each group were different, while the domain varaibles were the same.


##Final Data 
The final data is a dataframe with dimensions 180*81 . There were a total to 30 individuals and each performed six activities(30 x 6=180). The combination of the variables "subject-id" and " activity_name" is a unique identifier. Each of the remaining 79 variable is the mean of the mean and standard deviation features of the raw dataset. 

##Transformations
In order to arrive at the final data set the raw data went through different stages of merging to finally contain the train and test data in one data/data frame, along with the subject_id and activity names. Only the variables/features which provided the mean and standard deviation were kept in the dataframe, while the rest were dropped. 

This dataframe was then reshaped in the long format and was e casted into a wide format providing the average of each variable for each combination of subject_id and activity. The details of this process can be found in the README.md file. 



##Summary of Variables

```{r, echo=FALSE}
setwd("C://Users//Sara//Desktop//Sara//Course Assignment")
getwd()

final_data<-read.table(".//final_data.csv")
summary(final_data)
```

subject_id                       : int  1 1 1 1 1 1 2 2 2 2 ...

activity_name                    : Factor w/ 6 levels "LAYING","SITTING",..: 1 2 3 4 5 6 1 2 3 4 ...

time_bodyacc_mean-x              : num  0.222 0.261 0.279 0.277 0.289 ...

time_bodyacc_mean-y              : num  -0.04051 -0.00131 -0.01614 -0.01738 -0.00992 ...

time_bodyacc_mean-z              : num  -0.113 -0.105 -0.111 -0.111 -0.108 ...

time_bodyacc_std-x               : num  -0.928 -0.977 -0.996 -0.284 0.03 ...

time_bodyacc_std-y               : num  -0.8368 -0.9226 -0.9732 0.1145 -0.0319 
...

time_bodyacc_std-z               : num  -0.826 -0.94 -0.98 -0.26 -0.23 ...

time_gravityacc_mean-x           : num  -0.249 0.832 0.943 0.935 0.932 ...

time_gravityacc_mean-y           : num  0.706 0.204 -0.273 -0.282 -0.267 ...

time_gravityacc_mean-z           : num  0.4458 0.332 0.0135 -0.0681 -0.0621 ...

time_gravityacc_std-x            : num  -0.897 -0.968 -0.994 -0.977 -0.951 ...

time_gravityacc_std-y            : num  -0.908 -0.936 -0.981 -0.971 -0.937 ...

time_gravityacc_std-z            : num  -0.852 -0.949 -0.976 -0.948 -0.896 ...

time_bodyaccjerk_mean-x          : num  0.0811 0.0775 0.0754 0.074 0.0542 ...

time_bodyaccjerk_mean-y          : num  0.003838 -0.000619 0.007976 0.028272 0.02965 ...

time_bodyaccjerk_mean-z          : num  0.01083 -0.00337 -0.00369 -0.00417 -0.01097 ...

time_bodyaccjerk_std-x           : num  -0.9585 -0.9864 -0.9946 -0.1136 -0.0123 ...

time_bodyaccjerk_std-y           : num  -0.924 -0.981 -0.986 0.067 -0.102 ...

time_bodyaccjerk_std-z           : num  -0.955 -0.988 -0.992 -0.503 -0.346 ...

time_bodygyro_mean-x             : num  -0.0166 -0.0454 -0.024 -0.0418 -0.0351 ...

time_bodygyro_mean-y             : num  -0.0645 -0.0919 -0.0594 -0.0695 -0.0909 ...

time_bodygyro_mean-z             : num  0.1487 0.0629 0.0748 0.0849 0.0901 ...

time_bodygyro_std-x              : num  -0.874 -0.977 -0.987 -0.474 -0.458 ...

time_bodygyro_std-y              : num  -0.9511 -0.9665 -0.9877 -0.0546 -0.1263 ...

time_bodygyro_std-z              : num  -0.908 -0.941 -0.981 -0.344 -0.125 ...

time_bodygyrojerk_mean-x         : num  -0.1073 -0.0937 -0.0996 -0.09 -0.074 ...

time_bodygyrojerk_mean-y         : num  -0.0415 -0.0402 -0.0441 -0.0398 -0.044 ...

time_bodygyrojerk_mean-z         : num  -0.0741 -0.0467 -0.049 -0.0461 -0.027 ...

time_bodygyrojerk_std-x          : num  -0.919 -0.992 -0.993 -0.207 -0.487 ...

time_bodygyrojerk_std-y          : num  -0.968 -0.99 -0.995 -0.304 -0.239 ...

time_bodygyrojerk_std-z          : num  -0.958 -0.988 -0.992 -0.404 -0.269 ...

time_bodyaccmag_mean             : num  -0.8419 -0.9485 -0.9843 -0.137 0.0272 ...

time_bodyaccmag_std              : num  -0.7951 -0.9271 -0.9819 -0.2197 0.0199 ...

time_gravityaccmag_mean          : num  -0.8419 -0.9485 -0.9843 -0.137 0.0272 ...

time_gravityaccmag_std           : num  -0.7951 -0.9271 -0.9819 -0.2197 0.0199 ...

time_bodyaccjerkmag_mean         : num  -0.9544 -0.9874 -0.9924 -0.1414 -0.0894 ...

time_bodyaccjerkmag_std          : num  -0.9282 -0.9841 -0.9931 -0.0745 -0.0258 ...

time_bodygyromag_mean            : num  -0.8748 -0.9309 -0.9765 -0.161 -0.0757 ...

time_bodygyromag_std             : num  -0.819 -0.935 -0.979 -0.187 -0.226 ...

time_bodygyrojerkmag_mean        : num  -0.963 -0.992 -0.995 -0.299 -0.295 ...

time_bodygyrojerkmag_std         : num  -0.936 -0.988 -0.995 -0.325 -0.307 ...

freq_bodyacc_mean-x              : num  -0.9391 -0.9796 -0.9952 -0.2028 0.0382 ...

freq_bodyacc_mean-y              : num  -0.86707 -0.94408 -0.97707 0.08971 0.00155 ...

freq_bodyacc_mean-z              : num  -0.883 -0.959 -0.985 -0.332 -0.226 ...

freq_bodyacc_std-x               : num  -0.9244 -0.9764 -0.996 -0.3191 0.0243 ...

freq_bodyacc_std-y               : num  -0.834 -0.917 -0.972 0.056 -0.113 ...

freq_bodyacc_std-z               : num  -0.813 -0.934 -0.978 -0.28 -0.298 ...

freq_bodyacc_meanfreq-x          : num  -0.1588 -0.0495 0.0865 -0.2075 -0.3074 ...

freq_bodyacc_meanfreq-y          : num  0.0975 0.0759 0.1175 0.1131 0.0632 ...

freq_bodyacc_meanfreq-z          : num  0.0894 0.2388 0.2449 0.0497 0.2943 ...

freq_bodyaccjerk_mean-x          : num  -0.9571 -0.9866 -0.9946 -0.1705 -0.0277 ...

freq_bodyaccjerk_mean-y          : num  -0.9225 -0.9816 -0.9854 -0.0352 -0.1287 ...

freq_bodyaccjerk_mean-z          : num  -0.948 -0.986 -0.991 -0.469 -0.288 ...

freq_bodyaccjerk_std-x           : num  -0.9642 -0.9875 -0.9951 -0.1336 -0.0863 ...

freq_bodyaccjerk_std-y           : num  -0.932 -0.983 -0.987 0.107 -0.135 ...

freq_bodyaccjerk_std-z           : num  -0.961 -0.988 -0.992 -0.535 -0.402 ...

freq_bodyaccjerk_meanfreq-x      : num  0.132 0.257 0.314 -0.209 -0.253 ...

freq_bodyaccjerk_meanfreq-y      : num  0.0245 0.0475 0.0392 -0.3862 -0.3376 ...

freq_bodyaccjerk_meanfreq-z      : num  0.02439 0.09239 0.13858 -0.18553 0.00937 ...

freq_bodygyro_mean-x             : num  -0.85 -0.976 -0.986 -0.339 -0.352 ...

freq_bodygyro_mean-y             : num  -0.9522 -0.9758 -0.989 -0.1031 -0.0557 ...

freq_bodygyro_mean-z             : num  -0.9093 -0.9513 -0.9808 -0.2559 -0.0319 ...

freq_bodygyro_std-x              : num  -0.882 -0.978 -0.987 -0.517 -0.495 ...

freq_bodygyro_std-y              : num  -0.9512 -0.9623 -0.9871 -0.0335 -0.1814 ...

freq_bodygyro_std-z              : num  -0.917 -0.944 -0.982 -0.437 -0.238 ...

freq_bodygyro_meanfreq-x         : num  -0.00355 0.18915 -0.12029 0.01478 -0.10045 ...

freq_bodygyro_meanfreq-y         : num  -0.0915 0.0631 -0.0447 -0.0658 0.0826 ...

freq_bodygyro_meanfreq-z         : num  0.010458 -0.029784 0.100608 0.000773 -0.075676 ...

freq_bodyaccmag_mean             : num  -0.8618 -0.9478 -0.9854 -0.1286 0.0966 ...

freq_bodyaccmag_std              : num  -0.798 -0.928 -0.982 -0.398 -0.187 ...

freq_bodyaccmag_meanfreq         : num  0.0864 0.2367 0.2846 0.1906 0.1192 ...

freq_bodybodyaccjerkmag_mean     : num  -0.9333 -0.9853 -0.9925 -0.0571 0.0262 ...

freq_bodybodyaccjerkmag_std      : num  -0.922 -0.982 -0.993 -0.103 -0.104 ...

freq_bodybodyaccjerkmag_meanfreq : num  0.2664 0.3519 0.4222 0.0938 0.0765 ...

freq_bodybodygyromag_mean        : num  -0.862 -0.958 -0.985 -0.199 -0.186 ...

freq_bodybodygyromag_std         : num  -0.824 -0.932 -0.978 -0.321 -0.398 ...

freq_bodybodygyromag_meanfreq    : num  -0.139775 -0.000262 -0.028606 0.268844 0.349614 ...

freq_bodybodygyrojerkmag_mean    : num  -0.942 -0.99 -0.995 -0.319 -0.282 ...

freq_bodybodygyrojerkmag_std     : num  -0.933 -0.987 -0.995 -0.382 -0.392 ...

freq_bodybodygyrojerkmag_meanfreq: num  0.176 0.185 0.334 0.191 0.19 ...

