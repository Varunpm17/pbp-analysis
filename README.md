# NFL Play By Play Data and the Use of the Shotgun Formation

## Overview
An analysis of NFL Play by Play data from 2013 to 2020. This project looks into the NFL offenses use of the shotgun formation in order to determine if teams are more likely to be successfull when they employ a shotgun heavy offense. As an aside the shotgun formation is a NFL formation in which the Quarterback stands 7 yards behind the line of scrimmage giving him more time to asses the playing field and react to the defense. 

NFL play by play data was found on http://nflsavant.com/about.php a site dedicated to providing advanced NFL statistics, all data was compiled from publicly available sources. 

## Technologies Used
UNIX, Python, Pandas, Numpy, Matplotlib, Scipy

## The Data
Originally there were seven different datasets one for each year ranging from 2013 to 2020. Given that they were all formatted similarly I used the UNIX command awk 'FNR==1 && NR!=1{next;}{print}' *.csv to merge all the csv's into one aggregate file. After this file was generated performed the necessary data cleaning (removing bad rows and replacing Nan values) in the pbp-EDA notebook. The final cleaned dataframe contains 364590 rows and has 41 different features. 

Distribution of Each Offensive Formation: 

<img src="https://github.com/Varunpm17/pbp-analysis/blob/main/images/FormationDistribution.png" width="450" height="450">

Shotgun Formation Usage Compared to Total Formation Usage Per Team:

<img src="https://github.com/Varunpm17/pbp-analysis/blob/main/images/ShotgunsBarComparisonPerTeam.png" width="600" height="450">

## Analysis
The primary goal was to test whether or not teams with high shotgun usage fared better than balanced teams. I grouped the teams into two categories if the teams shogtgun formation count / total formation count was greater than the mean shogtgun formation count / total formation count then they would be classified as a heavy shotgun user team. Once I had created these two groups I performed a Two Sample Approximate Test of Population Means (Welsh's t-test) after taking 350 samples from each group (each sample representing total offensive yards in a game). With an alpha threshold of 0.2 the p-value I obtained was 0.5110 which far exceeded the threshold. Thus I was able to conclude that there is no difference in success between shotgun heavy offenses and balanced offenses. 
