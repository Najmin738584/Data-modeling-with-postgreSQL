## Project : Data Modeling with Postgres

A startup named Sparkify wants to analyze user activities using their song and
user data. The current data is spread among several JSON files, making it hard
to query and analyze.

This project is aims to create a database schema and ETL pipeline to load song and user data to a
Postgres database which make it easy to query and analyze data.

## Datasets

Data is collected for song and user activities in two directories:
`data/log_data` and `data/song_data`, using JSON files.


## Schema

The schema used for this exercise is the Star Schema: There is one main fact table containing all the measures associated to each event (user song plays), and 4 dimentional tables, each with a primary key that is being referenced from the fact table.This includes the following tables.

Fact Table : -

songplays - records in log data associated with song plays i.e. records with page NextSong
            songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

Dimension Tables :- 

1] users - user_id, first_name, last_name, gender, level
2] songs - song_id, title, artist_id, year, duration
3] artists - artist_id, name, location, latitude, longitude
4] time - start_time, hour, day, week, month, year, weekday


## Build
 
 Pre-requisites:

- Python 3
- PostgreSQL Database


### User setup

You Can run the following commands under psql to setup user access to
Postgres and create the initial `sparkifydb` database:

``` sql
CREATE ROLE student WITH ENCRYPTED PASSWORD 'student';
ALTER ROLE student WITH LOGIN;
ALTER ROLE student CREATEDB;
CREATE DATABASE sparkifydb OWNER student;

```
### Program execution
Execute the script to generate the database and its tables by executing '%run create_tables.py'.
Load the data and insert it to the database by executing '%run etl.py'.



