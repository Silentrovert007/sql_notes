# Refining Selections

</hr>

## Select Distinct:
 it is used to eliminate duplicate results, only getting distinct results in a query.
```sql
	SELECT DISTINCT author_lname from books;
```

To select distinct first name and last name we can use the concat function to concatenate the columns, applying the keyword distinct to the select.

```sql
	SELECT DISTINCT CONCAT(author_fname, ' ', author_lname);
```

The easiest way tho do the distinct selection of multiple data is:

```sql
	SELECT DISTINCT author_fname, author_lname
```


## ORDER BY
 It is one of the ways of sorting the data in the database during the selection. the order comes after the select.

```sql
	SELECT book_id, author_lname
	FROM books
	ORDER BY authoe_lname;

```

the above query is gonna order the results of the last name alphabetically, and this is gonna reflect in all the rows.

The default order is ascending. to change that, whe have to specify that we want the descending order. this works both for strings and numbers.

*note:*
```sql
	SELECT title, author_fname, author_lname
	FROM books
	ORDER BY 2;
```
The `Order by 2` is just a way to say that we want to order by the second column(in the selection).

It is also possible to order by multiple columns;

```sql
	SELECT author_fname, author_lname 
	FROM books
	ORDER BY author_lname, author_fname;
-- Here we can apply the asc or desc depending on the column we want to apply them.
```

It is also possible order by columns that are not necessarily part of of the table, but are resilts or values that we asked sql for.

```sql
	SELECT CONCAT(author_fname, ' ', author_lname) as author FROM books ORDER BY author;
-- here we used an alias, and then we ordered by it.
```

## LIMIT
LIMIT allows us to control the amount of results we get from the query. sometimes it is more useful while used along with sorting.

```sql
	SELECT title, released_year from books
	 limit 5;
-- Without the order by.
```

```sql
	 select book_id, title, released_year from books order by released_year limit 5;	
-- with order by.
```

it is possible to select a subset in the middle of the row instead of having all the limit. to do that we set the limit to something like `LIMIT 1, 5`. this means 
that 5 results are gonna be printed to the screen, but instead of startig to count at zero, it is going to start counting at 1. And, the very first row is not gonna 
be included.


## LiKE
Like is used for better searching.
here the search is not based on an exact match.

```sql
	SELECT author_fname from books where author_fname LIKE '%da%';
```


besides the percent sign, we can also use the underscore sign, which means, *exactly one character*. One _ means 1 characters, two _ 2 characters, and so on, and so 
fourth.
```sql
	SELECT author_fname from books where author_fname LIKE '____';
	-- looks for first names with exact 4 characters.
	-- They can possibly be combined
```
*Notes:*
* If we need to find something with a percent sign in it, we use `like '%/%%`
* use use the exact same syntax to escape an underscore: `like '%\_%'`

</br>
<br>

## Practice
1. Select all titles that contain 'stories'

--> `select title from books where title like '%stories%';`

2. find the longest book.

--> `select title, pages from books order by pages desc limit 0, 1;`

3. Print a summary containing the title and the year, for the 3 most recent books.

--> `select concat(title,' - ',released_year)as summary from books order by released_year desc limit 3;`

4. select all books with an author last name with a space.

--> `select title, author_lname from books where author_lname like '% %';`

5. find the 3 books with the lowest stock, select title, year and stock.

--> `select title, released_year, stock_quantity from books order by stock_quantity limit 3;`

6. Print title and author last name, sorted first by the author last name and then by the title.
-- > `select title, author_lname from books order by author_lname, title;`

7. make that thing happen, sort by the last name:

--> `select upper(concat('my favourite author is ', author_fname, ' ', author_lname))as yell from books order by author_lname;`

