# Project 1: Data Modeling with Postgres

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.


Document Process
Do the following steps in your README.md file.

Discuss the purpose of this database in the context of the startup, Sparkify, and their analytical goals.
State and justify your database schema design and ETL pipeline.
[Optional] Provide example queries and results for song play analysis.
Here's a guide on Markdown Syntax.

## Datasets Used

### Song Dataset

The first dataset is a subset of real data from the Million Song Dataset. Each file is in JSON format and contains metadata about a song and the artist of that song. The files are partitioned by the first three letters of each song's track ID. For example, here are filepaths to two files in this dataset.

### Log Dataset

The second dataset consists of log files in JSON format generated by this event simulator based on the songs in the dataset above. These simulate activity logs from a music streaming app based on specified configurations.

## Setup Instructions

1. Install requirements with *pip3 install -r library_req.txt*.
2. Set up a local PostgreSQL instance. Please see detailed instructions in the PostgreSQL documentation.

## Repository files

1. *test.ipynb* displays the first few rows of each table to let you check the database.
2. *create_tables.py* drops and creates your tables. You run this file to reset your tables before each time you run your ETL scripts.
3. *etl.ipynb* reads and processes a single file from song_data and log_data and loads the data into your tables. This notebook contains detailed instructions on the ETL process for each of the tables.
4. *etl.py* reads and processes files from song_data and log_data and loads them into your tables. You can fill this out based on your work in the ETL notebook.
5. *sql_queries.py* contains all your sql queries, and is imported into the last three files above.
6. *library_req.txt* lists all libraries required to run the scripts.
7. *README.md* provides discussion on your project.

## Program execution

1. Run *python3 create_tables.py* to setup the database and the required tables
2. Run *python3 etl.py* to load and insert data into the database.


## Schema Design

### Fact Table 

    1. songplays - stores the records in log data associated with song plays i.e. records with page.

### Dimension Tables

    1. users - stores the users in the app.
    2. song - stores the songs in the music database.
    3. artists - stores the artists the in music database.
    4. time - stores the timestamps of records in songplays broken down into specific units.
    
## Purpose of this database

This database is created specifically to answer questions such as what songs users are listening to, which songs are popular in a specific area, which artist is most listened to, and more. Lots of possibilities that can be answered, and since the data is organised in a way specifically for analysis and in a single database, Sparkify or any user would be able to use it with ease.