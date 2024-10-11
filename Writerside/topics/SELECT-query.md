# SELECT

The SELECT statement is used fetch data from a database table, which returns the data in the form of result table.

These results are called result-sets.

## Syntax

The basic syntax of select statement is as follows:

```sql
SELECT column1, column2, columnN FROM table_name;
```

In our school database, let's create a table called lecturers and insert the following data to help us better demonstrate
everything.

```sql
CREATE TABLE lecturers (
	id SERIAL PRIMARY KEY,
	first_name VARCHAR(50) NOT NULL,
	last_name VARCHAR(50) NOT NULL,
	email VARCHAR(50) NOT NULL UNIQUE,
	location VARCHAR(50) NOT NULL,
	age INT NOT NULL
);

INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (1, 'Arney', 'Sharman', 'asharman0@ox.ac.uk', 'Apt 392', 63);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (2, 'Pepita', 'Weekland', 'pweekland1@apache.org', 'Suite 27', 53);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (3, 'Inglis', 'Gifford', 'igifford2@accuweather.com', 'PO Box 98326', 50);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (4, 'Gwenny', 'Eberlein', 'geberlein3@mit.edu', '1st Floor', 26);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (5, 'Stefa', 'McCloud', 'smccloud4@paypal.com', 'Room 1442', 68);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (6, 'Alfons', 'Terbeck', 'aterbeck5@soup.io', '6th Floor', 56);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (7, 'Bondon', 'Fennessy', 'bfennessy6@answers.com', 'Suite 23', 31);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (8, 'Ingelbert', 'Gomer', 'igomer7@amazon.co.uk', 'Apt 920', 55);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (9, 'Pearline', 'Parsley', 'pparsley8@sogou.com', 'Apt 431', 52);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (10, 'Sadye', 'Baccus', 'sbaccus9@diigo.com', 'PO Box 77938', 35);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (11, 'Else', 'Marini', 'emarinia@va.gov', 'PO Box 50572', 51);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (12, 'Amye', 'Brayley', 'abrayleyb@amazon.co.uk', 'Room 906', 47);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (13, 'Breena', 'Pettendrich', 'bpettendrichc@state.gov', 'Room 1305', 63);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (14, 'Glen', 'Beavan', 'gbeavand@wp.com', '15th Floor', 58);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (15, 'Giacopo', 'Petett', 'gpetette@360.cn', '15th Floor', 35);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (16, 'Dallon', 'Bonnett', 'dbonnettf@mashable.com', 'Suite 41', 55);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (17, 'Forrester', 'Berrecloth', 'fberreclothg@fda.gov', 'Suite 8', 48);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (18, 'Kai', 'Exall', 'kexallh@slate.com', 'Room 303', 53);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (19, 'Vic', 'Cicconettii', 'vcicconettiii@lycos.com', 'Apt 1737', 33);
INSERT INTO lecturers (id, first_name, last_name, email, location, age) VALUES (20, 'Kata', 'Wordesworth', 'kwordesworthj@ycombinator.com', '4th Floor', 27);
```

Let's get all the lecturers, we want the first_name, last_name and email fields only:

```sql
SELECT first_name, last_name, email FROM lecturers;
```

![select some fields](select-some-fields.png)

If you want to fetch all the fields, you can use the asterisk symbol (\*) to mean all the fields:

```sql
SELECT * FROM lecturers;
```

![select everything](select-everything.png)
