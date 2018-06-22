# Create(생성), Read(읽기), Update(갱신), Delete(삭제)

CREATE TABLE Users(name VARCHAR(128), email VARCHAR(128));

INSERT INTO Users(name, email) VALUES('Kristin', 'kf@umich.edu')

INSERT INTO Users(name, email) VALUES('Kristin', 'kf@umich.edu');
INSERT INTO Users(name, email) VALUES('Ted', 'ted@umich.edu');
INSERT INTO Users(name, email) VALUES('Charles', 'csev@umich.edu');
INSERT INTO Users(name, email) VALUES('Kane', 'ka@umich.edu');

DELETE FROM Users where email = 'kf@umich.edu'

UPDATE Users SET name = 'Olsen' WHERE email = 'os@umich.edu'

SELECT * FROM Users WHERE email = 'csev@umich.edu'

SELECT * FROM Users ORDER BY email 

SELECT * FROM Users ORDER BY email DESC


※ by PY4E(https://www.py4e.com/)

