# Quiz 42
## SQL Command

```.sql
attach database "movie_database" as db;
CREATE TABLE if not exists movies(
    id INTEGER PRIMARY KEY,
    name text,
    producer text,
    director text,
    category text,
    budget INTEGER,
    year INTEGER);

INSERT INTO movies(name,producer,director,category,budget,year) VALUES ('Forrest Gump','Paramount Pictures','Wendy Finerman','Comedy Drama','55000000','1994');
INSERT INTO movies(name, producer, director, category, budget, year) VALUES ('Catch Me If You Can','DreamWorks Pictures','Steven Spieldberg','Crime Comedy Drama','52000000','2002');
```

## SQL

![quiz043 sql](https://user-images.githubusercontent.com/112055062/225376055-db7bc9e2-3776-44e3-bcbb-60b7eaa37b31.png)

## Table

![quiz043 table](https://user-images.githubusercontent.com/112055062/225376128-66e5b60c-39aa-471c-999f-d0253380484f.png)
