# LIMIT, OFFSET, FETCH

## LIMIT
Used to limit the amount of data returned by the SELECT statement. For example selecting only the first 10 records.

The basic syntax is as follows

```SQL
SELECT column1, column2, columnN FROM table_name LIMIT number_of_rows;
```

Let's select only the first 10 records from our lecturers table:

```SQL
SELECT * FROM lecturers LIMIT 10;
```

![limit](limit.png)

## OFFSET
The OFFSET clause is used to skip a specified number of rows before starting to return rows from the result set.

It is typically used in combination with LIMIT or FETCH to paginate results, allowing you to retrieve data in chunks 
or skip over parts of the dataset.

The basic syntax is as follows:
```SQL
SELECT column1, column2, columnN FROM table OFFSET number_of_rows_to_skip;
```

Let's select records from our lectures table but skip the first 5 records:

```SQL
SELECT * FROM lecturers OFFSET 5;
```

![offset](offset.png)

## Combining OFFSET and LIMIT
We can combine OFFSET and LIMIT to get only a portion of the data back.

```SQL
SELECT column1, column2, columnN FROM table_name 
OFFSET number_of_rows_to_skip LIMIT number_of_rows;
```
Let's select only 10 records starting from record number 5.

```SQL
SELECT * FROM lecturers OFFSET 5 LIMIT 10;
```

![limit and offset](limit-and-offset.png)

## FETCH
LIMIT is not a keyword by SQL standards.

The actual way of limiting the results coming from a table is by using the FETCH keyword.

The basic syntax is as follows:

```SQL
SELECT column1, column2, columnN FROM table_name 
FETCH {FIRST | NEXT} row_count {ROW | ROWS} ONLY;
```

- ```FIRST``` and ```NEXT```: Both are interchangeable and indicate the number of rows to return.
- ```row_count```: Specifies the number of rows to return.
- ```ROW``` or ```ROWS```: Used to indicate the row count. ROW is used if you expect a single row, and ROWS is for multiple rows.
- ```ONLY```: Ensures that no more than the specified number of rows are fetched.

Let's fetch the first 10 rows
```SQL
SELECT * FROM lecturers FETCH FIRST 10 ROWS ONLY;
```

![fetch first 10 rows](fetch-first.png)

We can also use NEXT in the place of FIRST, it will work similar to FIRST.

```SQL
SELECT * FROM lecturers FETCH NEXT 10 ROWS ONLY;
```

![fetch next 10 rows](fetch-next.png)

When fetching one row, we use ROW instead of ROWS.

```SQL
SELECT * FROM lecturers FETCH FIRST 1 ROW ONLY;
```
![fetch first row only](fetch-first-row-only.png)

When fetching only one row, we can remove the number:

```SQL
SELECT * FROM lecturers FETCH FIRST ROW ONLY;
```

![first row only](first-row-only.png)