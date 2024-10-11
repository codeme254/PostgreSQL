# Constraints in-depth

Constraints are the rules enforced on data columns on table.

They are used to prevent invalid data from being entered into the database, ensuring the accuracy and reliability of 
the data in the database.

Some commonly used constraints available in PostgreSQL are:
- **NOT NULL constraint**: ensures that a column cannot have NULL values.
- **UNIQUE constraint**: ensures that all values in a column are different.
- **PRIMARY key**: uniquely identifies each row/record in a database table.
- **FOREIGN key**: constraints data based on columns in other tables.
- **CHECK**: ensures that all values in a column satisfy a certain condition.


## NOT NULL
By default, a column can hold NULL values (can be empty).

If you do not want a column to have a NULL value, then you need to define such constraint on this column, specifying that 
empty values are not allowed into the column.

```sql
CREATE TABLE test(
    username VARCHAR(50) NOT NULL,
    first_name VARCHAR(50) NOT NULL
);
```
In this example, the username and the first_name field must always have a value when inserting a new record.

## UNIQUE
This constraint prevents two records from having identical values in a particular column. It ensures that all values in a 
column (or a group of columns) are distinct.

For example, two or more users can't have similar email addresses, this is where the UNIQUE constraint comes into play.

```sql
CREATE TABLE test(
    username VARCHAR(50) UNIQUE,
    email_address VARCHAR(50) UNIQUE
);
```
In this example, the username and the email_address columns cannot have duplicate values.

## PRIMARY KEY
Uniquely identifies each record in a database table.

It is a combination of NOT NULL and UNIQUE constraints.

NOTE: **There can be more UNIQUE columns in a table but only one PRIMARY KEY in a table**

It is important for tables to always have primary keys.

Primary keys become foreign keys in other tables when creating relations among tables.

If a table has a primary key defined on any field(s), then you cannot have two records having the same value of that field(s).

It is always important to ensure that your table has a primary key, the pattern is usually to have an "id" field and make 
this field (column) to be the primary key.

```sql
CREATE TABLE test(
    id SERIAL PRIMARY KEY,
    username VARCHAR(50) UNIQUE,
    email_address VARCHAR(50) UNIQUE
);
```
The test table has three columns: id, username, and email_address. The id column is of type SERIAL and serves as the primary key, 
automatically generating a unique identifier (integer) for each row.

## FOREIGN KEY
A foreign key constraint specifies that the values in a column (or a group of columns) must match the values appearing in some row of another table.

A FOREIGN KEY constraint establishes a relationship between two tables.

It ensures that the value in a column (or group of columns) matches the value in another table.

```sql
CREATE TABLE orders (
    order_id SERIAL PRIMARY KEY,
    user_id INT REFERENCES users(user_id),
    order_date TIMESTAMP NOT NULL
);
```

Here, the user_id in the orders table references the user_id in the users table, ensuring referential integrity.

## CHECK
A check constraint ensures that values in a column satisfy a specific condition.

```sql
CREATE TABLE test(
    id SERIAL PRIMARY KEY,
    email_address UNIQUE NOT NULL,
    age INT CHECK(age >= 15)
```
In this case, the CHECK constraint ensures that no record has the age entry below 15.