# Primary Keys

A primary key refers to a value in a column that uniquely identifies a record in a table.

Primary keys enforces two main constraints:
- **Uniqueness**: the value of the primary key column(s) must be unique for every row.
- **Not Null**: A primary key column cannot contain NULL values.

## Why Primary Keys are important
Primary keys are essential for maintaining the integrity of data and ensuring that each record in the table can be uniquely identified.

They are also critical for establishing relationships between tables in a relational database through **foreign keys**.

## Creating a Primary Key
When you create a table in PostgreSQL, you can define a column as the primary key using the PRIMARY KEY keyword. The syntax is straightforward:

```SQL
CREATE TABLE test(
    id SERIAL PRIMARY KEY,
    name VARCHAR(50),
    age INT
);
```

In this example, the id column is defined as the primary key. This means each student will have a unique id.

The SERIAL data type automatically generates sequential integer values, which is useful for primary keys.

## Composite Primary Keys / Composite Keys
In some cases, you may need a combination of columns to uniquely identify a record. This is called a composite primary key.

A **composite key** is a primary key that is made up of two or more columns.

```SQL
CREATE TABLE student(
    student_id SERIAL,
    national_id SERIAL,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    
    PRIMARY KEY (student_id, national_id)
);
```

## Adding a Primary Key to an existing table
If you have an existing table without a primary key, you can add one using the ALTER TABLE statement:

Note that, the column that you want to update to be the Primary Key should contain unique values.

Assuming you have students table with no Primary Key and it has a student_id column with unique values, you can update this
column to be the primary key as shown:

```SQL
ALTER TABLE students ADD PRIMARY KEY (student_id);
```