### ● Multi table Table SQL : primary key, join

```sql

CREATE TABLE "Artist"(
     "id" INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL UNIQUE,
	 "name" text)  
	                          
CREATE TABLE "Album"(
     "id" INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL UNIQUE,
	 artist_id INTEGER,
	 "title" TEXT)  

CREATE TABLE "Genre"(
     "id" INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL UNIQUE,
	 "name" TEXT)  
	 
CREATE TABLE "Track"(
     "id" INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL UNIQUE,
	 album_id INTEGER, genre_id, INTEGER, len INTEGER, rating INTEGER,
	 "title" TEXT, "count" INTEGER)  



INSERT INTO Artist (name) VALUES ('Led Zepplin')
INSERT INTO Artist (name) VALUES ('AC/DC')  


INSERT INTO Genre (name) VALUES ('Rock');
INSERT INTO Genre (name) VALUES ('Metal');  


INSERT INTO Album (title, artist_id) VALUES ('Who Made Who', 2);
INSERT INTO Album (title, artist_id) VALUES ('IV', 1);  


INSERT INTO Track (title, rating, len, count, album_id, genre_id)
    VALUES ( 'Black Dog', 5, 297, 0, 2, 1);

INSERT INTO Track (title, rating, len, count, album_id, genre_id)
    VALUES ('Stairway', 5, 482, 0, 2, 1);

INSERT INTO Track (title, rating, len, count, album_id, genre_id) 
    VALUES ('About to Rock', 5, 313, 0, 1, 2) ;
	
INSERT INTO Track (title, rating, len, count, album_id, genre_id) 
    VALUES ('Who Made Who', 5, 207, 0, 1, 2) ;



select Album.title, Artist.name from Album join Artist on Album.artist_id = Artist.id

select Track.title, Genre.name from Track join Genre on Track.genre_id = Genre.id

select Album.title, Album.artist_id, Artist.id, Artist.name from Album join Artist on Album.artist_id = Artist.id

select Track.title, Track.genre_id, Genre.id, Genre.name from Track join Genre

select Track.title, Genre.name from Track join Genre on Track.genre_id = Genre.id

select Track.title, Artist.name, Album.title, Genre.name from Track join Genre join Album join Artist on Track.genre_id = Genre.id and Track.album_id = Album.id and Album.artist_id = Artist.id


```


※ by PY4E(https://www.py4e.com/)
