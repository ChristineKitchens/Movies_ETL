# Extract, Transform, and Load with Wikipedia and Kaggle Movie Data

## Project Overview
The script in the [jupyter notebook]() combines and cleans data from Wikipedia and Kaggle for export into an SQL database.

## Instructions for Use
While Wikipedia and Kaggle datasets are available in this repository for use, data was originally obtained via this [web link]().

First, clone the repository to a local drive. Prior to opening and executing the [jupyter notebook](), create a new database in pgAdmin 4 called "movie_data". This is the database that the cleaned movie data will be written to. 

After creating the SQL database, create a new text document called "config.py". Write the following text:
```
db_password = 'YOUR SERVER PASSWORD'
```
, where the text string is the user password used to access the server housing the newly created "movie_data" database.

Open the [jupyter notebook](). Scroll to cell and confirm that the SQL connection path is correct. It should be formatted as follows:
```
connection_string = f"{username}:{password}@localhost:5432/{database_name}"
```
After confirming the connection path is correct, execute the entire notebook. 

## Resources
- Data Source:
  - [wikipedia]()
  - [kaggle metadata]()
  - [ratings data]()
- Software:
  - Jupyter Notebook
  - pgAdmin 4
