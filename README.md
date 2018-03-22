# lo-analysis-project

Udacity Full Stack NanoDegree Log Analysis Project

### Project Description
>Task is to create a reporting tool that prints out reports (in plain text) based on the data in the database. This reporting tool is a Python program using the psycopg2 module to connect to the database.
  
#### Setting up the database and Creating Views:

  1. Load the data in local database using the command:
  
  ```
    psql -d news -f newsdata.sql
  ```
  2. Use `psql -d news` to connect to database.
  
  3. Create views using:
  ```
create view numviews_view as (select title, author, count(*) as num from articles,log where log.path=CONCAT('/article/',articles.slug) group by articles.title,articles.author order by num desc);
  ```
#### Running the queries:
  Run news.py using:
  ```
    $ python news.py
  ```
