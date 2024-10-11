# Create a database

In this tutorial, we will cover how to create a database and connect to it using psql, as well as how to delete a database. Let's get started by launching your psql terminal.

## Creating a database
To create a database, we use the ```CREATE DATABASE``` query and pass the name of the database.
```sql
CREATE DATABASE database_name;
```
**NOTE:** in PostgreSQL, all your queries should end with a semicolon.

When we execute the query, it returns the string ```CREATE DATABASE```, this means the command was executed successfully.

![create database](create-database.png)

The command above will create a database but will not connect to it.

You can run the command \l in psql to list all the databases available on your PostgreSQL server.

![list all databases](list-databases.png)


At the bottom of the list, you'll see the 'test' database that we just created.

To connect to this database, we will run the command 
```sql
\c db_name
```

we will replace db_name with the name of our database, in this case test.

![connect to database](connect-to-database.png)

And that's how you create and connect to a database in psql.

## Deleting a database
To delete a database, we use the query:
```sql
DROP DATABASE database_name;
```
If successfully executed, the command will return the string ```DROP DATABASE```.  
psql doesn't allow you to delete a database that you're currently connected to. 
To delete a database, you first need to switch to a different database before proceeding with the deletion.  
Let's try to delete the 'test' database that we created earlier.  

![delete a database](delete-database.png)

