-- 4.1 SELECT title FROM movies;

-- 4.2 SELECT DISTINCT rating FROM movies;

-- 4.3 SELECT * FROM movies WHERE rating is NULL;

-- 4.4 SELECT * FROM MovieTheaters WHERE Movie is NULL;

-- 4.5 SELECT * FROM MovieTheaters LEFT JOIN Movies ON MovieTheaters.Movie = Movies.Code;

-- 4.6 SELECT * FROM Movies LEFT JOIN MovieTheaters ON Movies.Code = MovieTheaters.Movie;

-- 4.7 SELECT Title FROM Movies WHERE Code NOT IN ( SELECT Movie FROM MovieTheaters WHERE Movie IS NOT NULL);

-- 4.8 INSERT INTO Movies(Title,Rating) VALUES('One, Two, Three',NULL);

-- 4.9 UPDATE Movies SET Rating = 'G' WHERE Rating is NULL;

-- 4.10 DELETE FROM MovieTheaters WHERE Movie IN (SELECT Code FROM Movies WHERE Rating = 'NC-17');

