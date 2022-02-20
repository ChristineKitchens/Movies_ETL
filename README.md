# Extract, Transform, and Load with Wikipedia and Kaggle Movie Data

## Project Overview
The script in the jupyter notebook [ETL_create_database.ipynb](https://github.com/InRegards2Pluto/Movies_ETL/blob/58114a33673295e42db7d586b2b10934e8c8cdb3/ETL_create_database.ipynb) combines and cleans data from Wikipedia and Kaggle for export into an SQL database. The script was prepared as part of a mock excercise where movie data from different sources were used to prepare a dataset for a media streaming hackathon. The exercise is designed to implement the Extract, Transform, and Load process (i.e. ETL). 

## Instructions for Use
Both Wikipedia and Kaggle datasets are available in this repository for use. The Kaggle dataset pulls from the MovieLens dataset of over 20 million reviews and contains a metadata file with details about the movies from The Movie Database (TMDb).

First, clone the repository to a local drive. Prior to opening and executing the [jupyter notebook](https://github.com/InRegards2Pluto/Movies_ETL/blob/58114a33673295e42db7d586b2b10934e8c8cdb3/ETL_create_database.ipynb), create a new database in pgAdmin 4 called "movie_data". This is the database that the cleaned movie data will be written to. 

After creating the SQL database, create a new text document called "config.py". Write the following text:
```
db_password = 'YOUR SERVER PASSWORD'
```
, where the text string is the user password used to access the server housing the newly created "movie_data" database.

Open the [jupyter notebook](https://github.com/InRegards2Pluto/Movies_ETL/blob/58114a33673295e42db7d586b2b10934e8c8cdb3/ETL_create_database.ipynb). Scroll to the bottom of cell 3 and confirm that the SQL connection path is correct. It should be formatted as follows:
```
# Store connection string to local server as string. Format as
# connection_string = f"{username}:{password}@localhost:5432/{database_name}"
# For example, my connection string is:
db_string = f"postgresql://postgres:{db_password}@localhost:5432/movie_data"
```
After confirming the connection path is correct, execute the entire notebook. The last cell in the jupyter notebook will print statements updating progress on the export of the csvs to the SQL database. Once complete, open pgAdmin 4 and confirm that data has appeared.

## Resources
- Data Source:
  - [wikipedia-movies.json](https://github.com/InRegards2Pluto/Movies_ETL/blob/58114a33673295e42db7d586b2b10934e8c8cdb3/Resources/wikipedia-movies.json)
  - [movies_metadata](https://github.com/InRegards2Pluto/Movies_ETL/blob/58114a33673295e42db7d586b2b10934e8c8cdb3/Resources/movies_metadata.csv)
  - [ratings.csv](https://github.com/InRegards2Pluto/Movies_ETL/blob/58114a33673295e42db7d586b2b10934e8c8cdb3/Resources/ratings.csv)
- Software:
  - Jupyter Notebook
  - pgAdmin 4
