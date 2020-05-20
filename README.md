# Project: Data Modeling with Postgres

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.
 They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. The goal is to create a database schema and ETL pipeline for this analysis. As the Data Engineer, you'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results.

### Project Description
In this project, the engineer will apply skills in data modeling with Postgres and build an ETL pipeline using Python. Project completion will include defining a fact and dimension tables for a star schema for a particular analytic focus, and writing an ETL pipeline that transfers data from files in two local directories into the created tables in Postgres using Python and SQL.

### Schema for Song Play Analysis
The star schema that will be used to optimize queries on song play analysis includes the following tables:

##### Fact Table
`songplays` - records in log data associated with song plays i.e. records with page NextSong
    songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
    
##### Dimension Tables
`users` - users in the app
    user_id, first_name, last_name, gender, level
`songs` - songs in music database
    song_id, title, artist_id, year, duration
`artists` - artists in music database
    artist_id, name, location, latitude, longitude
`time` - timestamps of records in songplays broken down into specific units
    start_time, hour, day, week, month, year, weekday
    
###### Example Queries

*Get all data from paid users*
```
SELECT * FROM songplays WHERE level = 'paid';
```

*get all users whos location is in Florida*
```
SELECT user_id FROM songplays WHERE location LIKE '%FL%' GROUP BY user_id;
```

