# COALESCE

The COALESCE operator allows us to have a default value in case the first one is not present.

It is particularly useful when working with data that may contain NULL values, as ita allows you to provide default or 
alternative data when NULL is encountered.

Example
Suppose we have a table called "test":
```SQL
CREATE TABLE test (
    id SERIAL PRIMARY KEY,
    name VARCHAR(50),
    phone_number VARCHAR(20)
);
```

Add the following data:

```SQL
INSERT INTO test (name, phone_number)
VALUES ('John', '123-456-7890'), ('Jane', NULL), 
('Sam', '987-654-3210'), ('Kennedy', NULL);
```

When we select all the columns from the table, some records will have empty values in the phone_number fields as shown:

![no coalesce](coalesce-1.png)

Sometimes, we don't want this behavior.

To fix this, we can provide default values, for example 'N/A' where there is no phone number.

```SQL
SELECT *, COALESCE(phone_number, 'N/A') FROM test;
```

![coalesce](coalesce-2.png)

This has introduced a new field called COALESCE with each record having a default value ('N/A') in case they don't have a 
value for this column.

We can rename this field as shown:
```SQL
SELECT *, COALESCE(phone_number, 'N/A') AS contact_number FROM test;
```

![coalesce as](coalesce-as.png)

We can get rid of the phone_number field if we want:

```SQL
SELECT id, name, COALESCE(phone_number, 'N/A') AS contact_number FROM test;
```
![coalescing and removing the phone_number field](coalesce-and-remove-column.png)

