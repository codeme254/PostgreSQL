# GROUP BY

The group by clause is used to group rows that have the same values in specified columns into aggregate data.

It is typically used in combination with aggregate functions like COUNT(), SUM(), AVG(), MAX(), and MIN() to summarize the grouped data.

Basic syntax:

```SQL
SELECT column_x, aggregate_function(column_1) FROM table_name GROUP BY column_x;
```

Let's say we want to know how many lecturers there are for each age in our table, for example, we want to know how many 
lecturers are 68 years old, how many are 27 years old etc.

```SQL
SELECT age, COUNT(*) FROM lecturers GROUP BY age;
```

![group by](group-by.png)

## HAVING keyword
If we want to pass a condition to the GROUP BY clause, the WHERE clause won't work.

HAVING keyword is used to pass conditions to the GROUP BY clause.

Let's say we want to count how many lecturers there are for each age in our table above 40 years:

```SQL
SELECT age, COUNT(*) FROM lecturers GROUP BY age HAVING age > 40;
```

![Group by having](group-by-having.png)