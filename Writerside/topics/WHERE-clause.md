# WHERE clause

The WHERE clause is used to filter records in a query based on specified conditions.

It helps in retrieving only the rows that meet certain criteria, making queries more efficient by limiting the data returned.

The basic syntax for WHERE clause is as shown:

```SQL
SELECT column1, column2, columnN FROM table_name WHERE condition;
```

if you want all the columns:

```SQL
SELECT * FROM table_name WHERE condition;
```

- The condition is an expression that evaluates to TRUE, FALSE, or NULL.
- Only rows for which the condition is TRUE are included in the result set.

Let's retrieve all the lecturers who are 50 years old or greater.

```SQL
SELECT * FROM lecturers WHERE age >= 50;
```

![WHERE Clause in action](where.png)

## Using Logical Operators with WHERE (AND, OR)
We can also combine conditions using logical operators.

Let's find all lecturers whose age is above 50 and less than 60
```SQL
SELECT * FROM lecturers WHERE age > 50 AND age < 60;
```

![where with AND](where-with-and.png)

We could easily improve the query above to use the BETWEEN operator.

```SQL
SELECT * FROM lecturers WHERE age BETWEEN 51 AND 61;
```
![where with between](where-with-between.png)

Now let's use the OR operator with the WHERE clause to select all the teachers who are above 60 years or less than 30 years.

```SQL
SELECT * FROM lecturers WHERE age > 60 OR age < 30;
```

![where with OR](where-with-or.png)