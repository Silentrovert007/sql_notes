# Intro to CRUD
* CRUD is an acromym that stands for  Create Read Update and Delete.
* Create is when we create table and insert data.
* For Reading, we use the SELECT keyword, to select rows in the table and viewing their content.
    * select name from cats --> is going to give me only the names of the cats.
    
     ![alt text](./imgs/image-1.png)

    * select age from cats; --> displays the ages of the cats in the table.
    
    ![alt text](./imgs/image-2.png)
* to combine multiple columns we just neee dto separate their names woth commas.
    * Select name, age from cats --> gives us the names of the cats and their ages.
    
    ![alt text](./imgs/image-3.png)
* The where clause allows us to narrow down the rows we're working with. for exemple, `select * from cats where age = 4;`

 ![alt text](./imgs/image-4.png)

* select name, age from cats where age = 4:

    ![alt text](./imgs/image-5.png)

* select * from cats where name = 'egg';

    ![alt text](./imgs/image-6.png)

* it is not limited to select.

* For UPDATE, we use the update keyword to change data in the table. the syntax is `update table SET breed = 'junior'.

    ```sql
        update cats set age = 14 where name = 'Misty';
    ```
CAUTION: select before updtating.

* for Delete we use delete from  ats where name = 'something'; 

![alt text](./imgs/image-15.png)

* delete from table is giung to erase all the information in the table.

    ![alt text](./imgs/image-16.png)

### exercise 1.

* cat_id for all the rows

    ![alt text](./imgs/image-7.png)

* name and breed.

    ![alt text](./imgs/image-8.png)

* tabby cats

    ![alt text](./imgs/image-9.png)

* cat_id same as their age

    ![alt text](./imgs/image-10.png)

## Aliases

 it is useful to rename a column to make it shorter and easier to understand.
    
![alt text](./imgs/image-11.png)

to use aliases, we have to use the keyword as, folowed by the temporary name for the column we want to work with.

### Exercise 2 - updates

* change Jackson's name to Jack

    ![alt text](./imgs/image-12.png)

* change ringo's breed to British Shorthair

    ![alt text](./imgs/image-13.png)

* update both maine coons ages to be 12

    ![alt text](./imgs/image-14.png)


### Exrcise 4
* delete all 4 year old cat

![alt text](./imgs/image-17.png)

* delete all cats with their ids equal to their age.

![alt text](./imgs/image-18.png)

* Delete all the cats

![alt text](./imgs/image-19.png)


