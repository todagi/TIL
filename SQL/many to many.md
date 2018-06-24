### ● many to many relationship


***

CREATE TABLE User(
    id INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT UNIQUE,
	name TEXT UNIQUE,
	email text
	) ;

CREATE TABLE Course(
    id INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT UNIQUE,
	title TEXT unique
	) ;

CREATE TABLE Member (
    user_id     INTEGER,
    course_id   INTEGER,
	role        INTEGER,
    PRIMARY KEY (user_id, course_id)
    ) ;

INSERT INTO User (name, email) VALUES ('Jane', 'jane@tsugi.org');
INSERT INTO User (name, email) VALUES ('Ed', 'ed@tsugi.org');
INSERT INTO User (name, email) VALUES ('Sue', 'sue@tsugi.org');
INSERT INTO User (name, email) VALUES ('Charlse', 'cha@tsugi.org');

INSERT INTO course (title) VALUES ('Python');
INSERT INTO course (title) VALUES ('SQL');
INSERT INTO course (title) VALUES ('PHP');
INSERT INTO course (title) VALUES ('R');

INSERT INTO Member (user_id, course_id, role) VALUES (1, 1, 1);
INSERT INTO Member (user_id, course_id, role) VALUES (2, 1, 0);
INSERT INTO Member (user_id, course_id, role) VALUES (3, 1, 0);
INSERT INTO Member (user_id, course_id, role) VALUES (4, 1, 0);

INSERT INTO Member (user_id, course_id, role) VALUES (1, 2, 0);
INSERT INTO Member (user_id, course_id, role) VALUES (2, 2, 1);
INSERT INTO Member (user_id, course_id, role) VALUES (3, 2, 0);
INSERT INTO Member (user_id, course_id, role) VALUES (4, 2 ,0);

INSERT INTO Member (user_id, course_id, role) VALUES (1, 3, 0);
INSERT INTO Member (user_id, course_id, role) VALUES (2, 3, 0);
INSERT INTO Member (user_id, course_id, role) VALUES (3, 3, 1);
INSERT INTO Member (user_id, course_id, role) VALUES (4, 3, 0);

INSERT INTO Member (user_id, course_id, role) VALUES (4, 4, 0);

# role 변수가 연결 테이블에서 모델링됨

SELECT User.name, Member.role, Course.title 
From User JOIN Member Join Course 
ON Member.user_id = User.id AND Member.course_id = Course.id
ORDER BY course.title, Member.role DESC, User.name



※ by PY4E(https://www.py4e.com/)
