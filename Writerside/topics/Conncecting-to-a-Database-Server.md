# Connecting to a Database

PostgreSQL provides two primary tools for connecting to and managing databases:

- **psql**: A powerful command-line tool for executing SQL queries and database management tasks.
- **pgAdmin**: A user-friendly, graphical interface for database administration.  
Both tools are typically installed as part of the PostgreSQL installation process, offering flexibility based on your preference for command-line or graphical environments.  

In this guide, we will learn how to connect to a Database using **psql**

To connect to a database using psql:

### Launch psql
Click on windows **start** button (windows icon at the taskbar) and search for psql.  
Launch it by double-clicking on it. A terminal screen will be launched.

![connecting to psql - searching for psql](psql-connect-1.png)

### Specify the server
The first prompt that appears in the terminal is asking for the server where your database is hosted. If your database is hosted remotely, 
you’ll need to provide the server's URL here. By default, this option is set to localhost, meaning the database is hosted locally on your 
machine. If your database is on your local machine or you haven't set one up yet, you can leave this option as it is.

![connecting to a database - specifying the server](psql-connect-2.png)

### Specify the name of the database

The next prompt asks you to specify the database name. You can leave this option as it is for now, as it can be easily changed later.

![connecting to a database - specifying the database name](psql-connect-3.png)

### Specify the port

The next prompt asks you to enter the port number. This is the communication channel used to connect to the PostgreSQL server. 
By default, PostgreSQL uses port 5432. If you're running the server on the default port, you can leave this option unchanged. 
However, if your database is set up to use a different port, you'll need to enter that specific port number here.  

If you are new to all of this, you can leave the port as it is.

![connecting to a database - specifying the port](psql-connect-4.png)

### Specify the username
The next prompt asks for the username. This is the PostgreSQL user account that will be used to connect to the database. 
If you're using the default setup, the username is typically set to postgres, unless you've created a different user during the installation. 
If you're unsure or haven't set up any custom users, you can go with the default username.

![connecting to a database - specifying the username](psql-connect-5.png)

### Supply the password
The next prompt asks for the password associated with the username you provided in the previous step. If you're using the default settings, this will be the password you set during the installation process.  
Type your password and press Enter. If the password is correct, you will successfully connect to the database.  
Note: When typing your password, nothing will appear on the terminal screen (no characters or symbols). This is normal behavior, so just type your password and hit Enter.  

![connecting to a database - password and connect](psql-connect-6.png)

Ignore the warning!!

That's it, you have successfully connected to a database!

Next, let's look at how we can create our own database and connect to it.