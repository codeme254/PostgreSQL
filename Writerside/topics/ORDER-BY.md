# ORDER BY

The ORDER BY statement is used to sort the result set of a query by one or more columns.

You can specify the sorting order as ascending (```ASC```) which is also the default or descending (```desc```).

The basic syntax is as follows:

```SQL
SELECT column1, column2, columnN FROM table_name ORDER BY column_name [ASC|DESC];
```

or if you want all the columns returned

```SQL
SELECT * FROM table_name ORDER BY column_name [ASC|DESC];
```

Let's query everything from the lecturers table, and sort the result-set using the age column.  
If we don't specify ASC for Ascending or DESC for Descending, PostgreSQL will use ASC as the default.

```SQL
SELECT * FROM lecturers ORDER BY age;
```

![sort default](sort-default.png)

Let's now specify that the result-set should be sorted in Descending order by passing DESC.

```SQL
SELECT * FROM lecturers ORDER BY age DESC;
```
![sort descending](sort-descending.png)


Passing ASC will sort the results in ascending order (default).

```SQL
SELECT * FROM lecturers ORDER BY age ASC;
```

![sort ascending](sort-ascending.png)