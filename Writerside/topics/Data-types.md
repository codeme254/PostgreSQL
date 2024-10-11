# Data types

PostgreSQL supports a wide range of data types for handling different kinds of data.

These types can be grouped into categories, such as numeric types, character types, date/time types, boolean types, and more.

Here's an overview of most commonly used data types:

## Numeric Data Types
These data types are used for storing numbers, including integers and decimals.
- **SMALLINT**: Stores a small-range integer (-32,768 to 32,767).
- **INTEGER** / **INT**: stores a typical integer (-2,147,483,648 to 2,147,483,647).
- **BIGINT**: stores a large-range integer (-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807).
- **SERIAL**: auto-incrementing integer, often used as a primary key.
- **SMALLSERIAL**: small auto-incrementing integer (1 to 32767).
- **BIGSERIAL**: large auto-incrementing integer (1 to 9223372036854775807).

## Character Data Types
These types store text data.
- **CHAR(n)**: fixed-length character type. Always reserves n characters, even if the string is shorter (padded with spaces).
- **VARCHAR(n)**: variable-length character type. It stores up to n characters but only uses the actual length of the stored string.
- **TEXT**: variable-length character type that can store any length of text. There’s no need to specify a maximum length.

## Boolean Data Types
- **BOOLEAN**: stores TRUE, FALSE or NULL.

## Date/Time data types
These types are used for handling date and time values.
- **DATE**: stores date values (year, month, day) - without the time zone.
- **TIME**: stores time values (hour, minute, second) - without the time zone.
- **TIMESTAMP**: stores both date and time (without time zone).

## UUID data type
- **UUID**: Universally Unique IDentifier, often used for primary keys in distributed systems.

## Array Data Type
- **ARRAY**: allows columns to hold arrays of any data type.
```sql
CREATE TABLE test(
    names TEXT[]
);

INSERT INTO test (names) VALUES (ARRAY['Dennis', 'Alice', 'Bob']);
```

## ENUM types
Allows you to define a set of predefined values for a column.

For example, you can restrict a column to store only specific values like 'small', 'medium', or 'large'.

In the example below, we want the user_role to be either 'admin' or 'moderator'.
```sql
CREATE TYPE role AS ENUM('admin', 'moderator');

CREATE TABLE test(
    username UNIQUE NOT NULL,
    user_role role
);

INSERT INTO test(username, user_role) VALUES('codeme254', 'admin');
```

Trying to insert the record below will make psql throw an error:
```sql
INSERT INTO test(username, user_role) VALUES('jack', 'something else');
```