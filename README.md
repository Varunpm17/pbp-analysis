# NFL Play By Play Data and the Use of the Shotgun Formation

## Overview
An analysis of NFL Play by Play data from 2013 to 2020. This project looks into the NFL offenses use of the shotgun formation in order to determine if teams are more likely to be successfull when they employ a shotgun heavy offense. As an aside the shotgun formation is a NFL formation in which the Quarterback stands 7 yards behind the line of scrimmage giving him more time to asses the playing field and react to the defense. 

NFL play by play data was found on http://nflsavant.com/about.php a site dedicated to providing advanced NFL statistics, all data was compiled from publicly available sources. 

## Technologies Used
UNIX, Python, Pandas, Numpy, Matplotlib, Scipy

## The Data
Originally there were seven different datasets one for each year ranging from 2013 to 2020. Given that they were all formatted similarly I used the UNIX command awk 'FNR==1 && NR!=1{next;}{print}' *.csv to merge all the csv's into one aggregate file. After this file was generated performed the necessary data cleaning (removing bad rows and replacing Nan values) in the pbp-EDA notebook. The final cleaned dataframe contains 364590 rows and has 41 different features. 

Distribution of Each Offensive Formation: 

