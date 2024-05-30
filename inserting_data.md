# MySQL Notes
## Inserting Data

* to insert data into a table we use the keywords `insert into <table name>`. specifying the columns and the expected order for the data onsertion. it is done as follows:
    ```sql
        insert into cats (name, age)
        values ('Jetson', 7);
    ```
* To check if it worked we use the command `select * from <table name>`. 

    Eg:
    ```sql
        select * from cats;
    ```
* the example for when we have multiple inserts goes like this:
    ```sql
    insert into cats(name, age)
    values('meatball', 1),
          ('potato head', 15), 
          ('turkey', 1);
    ```

* Now, What is up with the NULL yes valuesin de described tables?
 ![alt text](image.png)

* In the above table, we see that the null valued is set to yes, in other words, this information tells us that these fields with the yeses in the null column, they're alowed to be empty. first name cand be empty, last name also, and age too.
* Here, NULL DOESN NOT MEAN ZERO. BUT MEANS THAT THERES NO INFORMATION AT ALL.
* To avoid the field to be null, we have to disallow this property while creting the table.
    ```sql
        create table cats2 (
        name varchar(100) not null,
        age int not null
        );
    ```
* The above code will create a table where the age column must not e empty. 
* De default columnn describes the default value for a column. I the table above it is set to NULL because the collumn does not have a default value. the default value is set durig the creation of the table, as follows:
    ```sql
        create table cats3 (
            name varchar(100) default 'unnamed',
            age int default 99
        )
    ```
#### important notes:
* Order Matters but consistency is important.
* if the string to be inserted has a quote in between, we need to escape it.
    ```sql
        insert into shops (name) value ('mario\' pizza');
    ```

## Intro to Primary Keys

* Primary keys is a unique identifier for each individual row.
* It can be added during the creation of the table.
* One way of specifying a primary key:
    ```sql
        create table unique_cats (
            cat_id int primary key,
            name varchar(100) not null,
            age int not null
        );
    ```
* Another way:
    ```sql
        create table unique_cats2 (
            cat_id int,
            name varchar(100) not null,
            age int not null,
            primary key (cat_id)
        );
    ```
* Primary keys kan never be null.
* Using auto_increment allow us not to keep inserting values for the primary keys. they're usually numerical values, and by default, they start at 1 and keep incrementing by 1.
    ```sql
        create table unique_cats3 (
            cat_id int auto_increment,
            name varchar(100),
            age int,
            primary key (cat_id)
        );
    ```



