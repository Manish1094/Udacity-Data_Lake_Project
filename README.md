# Data Lake Project With Apache Spark

## Introduction
A music streaming startup, Sparkify, has grown their user base and song database even more and want to move their data warehouse to a data lake. Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

our task is an ETL pipeline that extracts their data from S3, processes them using Spark, and loads the data back into S3 as a set of dimensional tables. This will allow their analytics team to continue finding insights in what songs their users are listening to.

## Data Source
The datasets used are retrieved from the s3 bucket and are in the JSON format. There are two datasets namely `log_data` and `song_data`.

## Database Schema Design 
The tables created include one fact table, `songplays` and four dimensional tables namely `users`, `songs`, `artists` and `time`. This follows the star schema principle which will contain clean data that is suitable for OLAP(Online Analytical Processing) operations which will be what the analysts will need to conduct to find the insights they are looking for.

## ETL Pipeline
The data gets that gets extracted will need to be transformed to to fit the data model in the target destination tables. For instance the source data for timestamp is in unix format and that will need to be converted to timestamp from which the year, month, day, hour values etc can be extracted which will fit in the relevant target time and songplays table columns. The script will also need to cater for duplicates, ensuring that they aren't part of the final data that is loaded in the tables.

# Project Files
etl.py : This script executed retrives the song & log data in the s3 bucket,transformthe data into fact and dimen