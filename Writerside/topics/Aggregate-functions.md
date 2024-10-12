# Aggregate functions

Aggregate functions in PostgreSQL are used to perform calculations on a set of rows and return a single result.

They are commonly used with the GROUP BY clause to summarize large sets of data, but can also be used on entire tables without grouping.

The most common aggregate functions are:
- ```COUNT()```: returns the number of rows in a set.
- ```SUM()```: returns the sum of a numeric column.
- ```AVG()```: calculates the average of a numeric column.
- ```MAX()```: returns the maximum value from a set of values.
- ```MIN()```: returns the minimum value from a set of values.

## COUNT()
Returns the number of rows that match a specified condition.

```SQL
SELECT COUNT(column_name) FROM table_name WHERE condition;
```

Let's count the number of lecturers who are above 50 years in our table:

```SQL
SELECT COUNT(age) FROM lecturers WHERE age > 50;
```

![count](count.png)


## SUM()
Returns the total sum of a numeric column.

```SQL
SELECT SUM(colum_name) FROM table_name;
```

Let's find the sum of all the ages in our lecturers table:

```SQL
SELECT SUM(age) FROM lecturers;
```

![sum](sum.png)

## AVG()
Returns the average of a numeric column.

```SQL
SELECT AVG(column_name) FROM table_name;
```

Let's find the average of the age field from our lecturers table:

```SQL
SELECT AVG(age) FROM lecturers;
```

![average](average.png)

## MIN()
Returns the minimum value from a numeric column.

```SQL
SELECT MIN(column_name) FROM table_name;
```

Let's find the lowest age lecturer from our lecturers table.

```SQL
SELECT MIN(age) FROM lecturers;
```

![min](min.png)

## MAX()
Returns the maximum value from a numeric column.

```SQL
SELECT MAX(column_name) FROM table_name;
```

Let's find the highest age from our lectures table.

```SQL
SELECT MAX(age) FROM lecturers;
```

![max](max.png)