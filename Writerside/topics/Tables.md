# Tables

A table in sql is a structured collection of data organized into **rows** and **columns**.  
Each row represents a single record, and each column represents a specific attribute of that record.  
Tables are the fundamental units for storing data in relational databases like PostgreSQL.  
For example, a table called employees might have columns like id, name, position, and salary, with each row holding the details for one employee.

To create a table in psql, we need to be connected to a database.  
Let's create a database called "school" and connect to it.

![create a database](tables-img-1.png)

Now we can start creating tables for our database.

## Creating a table

In SQL, tables can be classified based on the presence of constraints:

- A table with constraints
- A table without constraints.

A **constraint** is a rule or condition applied to a table's column(s) to ensure the integrity, accuracy, and reliability of the data.  
Constraints enforce specific requirements on the data being inserted or updated in a table, preventing invalid data from entering the database.

### Creating a table without constraints

To create a table without constraints, we use the query below:

```sql
CREATE TABLE table_name(
    column_name_1 data_type,
    column_name_2 data_type,
    ...
    column_name_n data_type
);
```

We use the `CREATE TABLE` query, and then we define the table name, inside the parenthesis, we list the columns present in our table and their data types.

A **data type** defines the kind of data that can be stored in that column such as number, text, text etc. and the operations that can be performed on the value.

If the query gets executed successfully, it returns the string `CREATE TABLE`.

Let's create a table called "Students" with the following columns; first name, last name, email address, registration number, age and date of admission.

```sql
CREATE TABLE Students(
    first_name VARCHAR(100),
    last_name VARCHAR(100),
    email_address VARCHAR(100),
    age INT,
    date_of_admission DATE
);
```

![Create table without constraints](create-table-no-constraints.png)

This SQL query creates a table called Students with five columns: first_name, last_name, email_address, age, and date_of_admission.
The first_name, last_name, and email_address columns are all variable-length strings with a maximum of 100 characters, while age is an integer,
and date_of_admission is a date field that stores the student's admission date.

### Creating a table with constraints

To create a table with constraints, we use the query below:

```sql
CREATE TABLE table_name(
    column_name_1 data_type constraint,
    column_name_2 data_type constraint,
    ...
    column_name_n data_type constraint
);
```

Let's create a table called "Lecturers" with the columns first_name, last_name, email_address, and work_id,
ensuring that none of these fields can be left empty during data insertion by applying the NOT NULL constraint to each column.

```sql
CREATE TABLE Lecturers(
    first_name VARCHAR(100) NOT NULL,
    last_name VARCHAR(100) NOT NULL,
    email_address VARCHAR(100) NOT NULL UNIQUE,
    work_id VARCHAR(100) NOT NULL UNIQUE
);
```

This SQL query creates a table named Lecturers with four columns: first_name, last_name, email_address, and work_id,
all of which are variable-length strings up to 100 characters. Each column has the NOT NULL constraint, ensuring that no
field can be left empty during data insertion. Additionally, the email_address and work_id columns are marked as UNIQUE,
preventing duplicate values for these fields. This table structure ensures data integrity by enforcing both uniqueness
and the requirement that all fields are filled in.

To view all the tables we have in our database, we can use the `\d` command as shown.

![List all tables](list-all-tables.png)

## Inserting data to a table

We can insert data into our table using the `INSERT INTO` query, we then specify the table name and inside parenthesis
we specify the columns that we want to insert, we then specify `VALUES` which takes a list of values we want to insert
matching the columns and their data types.

```sql
INSERT INTO table_name(
    column_1,
    column_2,
    ...
    column_n
) VALUES (column_1_value, column_2_value, ..., column_n_value);
```

Let's insert a record to the Lecturers table:

```sql
INSERT INTO Lecturers(
    first_name,
    last_name,
    email_address,
    work_id
) VALUES('John', 'Doe', 'johndoe@gmail.com', 'LEC001');
```

![insert into](insert-into.png)

You can confirm that the data has been inserted by running the query below (more about it later)
for now, just replace table_name with 'Lecturers':

```sql
SELECT * FROM table_name;
```

![select](select.png)

## Updating a table
