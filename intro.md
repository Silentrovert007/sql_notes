# MySQl Notes:

* ```Show databases;``` --> Show databases existing in the database server

* ```create database <name>;``` --> creates the database. it is important to specify the name, and the name must be specific. No spaces allowed, just underscores, upper and lowercase mixing.
Capitalization doesn't matter.

* ```Drop database <name> ```--> remove the database entirely, including its content.

* ```USE <Database name>``` -- > select the database to be worked on.
* `select database();` --> helps us to know in which database we're working on.


## Tables

* A relational database is just a bunch of tables. tables describe the format and the shape of our data, and hold collection of data that follow that shape.
* "A collection of related data held in a structured format witin a database"

* headers are called columns and the rows are the entries in the table:

#### Important datatypes:
* consistency is important
* numeric datatypes: int, smallint, tnyint, decimal, etc.
* String types: char, varchar, binary, etc.
* date types: date, datetime, tymestamp, etc...

    * for now: int and varchar(variable length string).

    * for varchar, we have to specify the maximum size. varchar(110) for example.



### creating tables
specify the name and the columns with the datatypes.

Eg:

```sql
create table cats 
(
    name varchar(50)
    age int
);
```


* to check if it worked, we use the command:
```SHOW TABLES;```.

* ```SHOW COLUMNS FROM <NAME OF THE TABLE>``` displays the infos related to the columns of the table inside the database.

* ```Desc <table namme>``` does the same thing as the command above. its an abbreviation for describe

* To delete tables, we use the comamand
```Drop table <table name>```

* To comment code, we use a double dash and a space before the statement to be commented.

