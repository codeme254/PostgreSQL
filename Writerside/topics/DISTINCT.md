# DISTINCT

The DISTINCT keyword in PostgreSQL is used to remove duplicate rows from the result set of a query.

When you apply DISTINCT, PostgreSQL will return only unique rows, ensuring that no duplicate records appear in the results.

Currently, when we query the lecturers table, we encounter duplicate values in the age field. If we want to retrieve only 
unique ages, we need to adjust our query to ensure only distinct values are returned

![duplicate records](distinct-1.png)

The basic syntax for distinct is as follows:

```SQL
SELECT DISTINCT column1, column2, columnN FROM table_name;
```

If we want to get unique ages:

```SQL
SELECT DISTINCT age FROM lecturers;
```
![select distinct on age](select-distinct-1.png)

## DISTINCT with multiple columns
When using DISTINCT on multiple columns, PostgreSQL **returns distinct combinations of values across these columns.**

Duplicate values in a column are acceptable as long as the combination of values across all other columns remains unique.

![select distinct with multiple columns](select-distinct-2.png)

We wanted unique values on the "age" column while maintaining the other columns, this would not work since the combination 
of these columns is unique across the table.

## DISTINCT ON
Allows you to select the first unique row for a specific column while returning other column values as well.

It’s useful when you want to get the first record for each group of unique values in a specific column.

The basic syntax for ```DISTINCT ON``` is as follows
```SQL
SELECT DISTINCT ON(column_name) column1, column2, columnN FROM table_name;
```
![select distinct on single column retaining other columns](select-distinct-3.png)