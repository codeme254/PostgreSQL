# Joins

A JOIN clause is used to combine rows from two or more tables, based on a related column between them.

Right now, we have two major tables in our database, lecturers table and units table as shown:

Lecturers table:

![lecturers table](j-lecturers-table.png)

Units table:

![units table](j-units-table.png)

The lecturer_id field in the units table refers to the id field in the lecturers table.

Assuming we wanted to print a report of each lecturer alongside the unit they teach, we would have to perform a join as shown.

```SQL
SELECT lecturers.first_name, lecturers.last_name, lecturers.email, 
units.unit_title FROM lecturers 
JOIN units ON lecturers.id = units.lecturer_id;
```

![simple join](simple-join.png)

This query retrieves the first name, last name, and email of lecturers along with the titles of the units they teach.

It uses a join between the lecturers and units tables, linking them through the lecturer_id to display relevant 
information for each lecturer associated with their respective unit.

## Types of Joins
- **INNER JOIN**: returns records that have matching values in both tables.
- **LEFT JOIN**: returns all records from the left table, and the matched records from the right table.
- **RIGHT JOIN**: returns all records from the right table, and the matched records from the left table.
- **FULL JOIN**: returns all records when there is a match in either left or right table

