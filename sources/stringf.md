# String functions
## Introduction
* String operations are different built-in operation that we can perform in text columns. mysql has a bunch onf them, but only the most famous are going to be covered.
* **source** command looks for the required sql script. the user does not need to specify the path. the command looks for the script in the whole file system, when it finds it, it runs all the commands in the script.
	* for example: `source book_data.sql`
* we have to meke sure that we are using the right database.

## Functions:

### 1. CONCAT -- combines data for cleaner output.
* without any sort of data or database, it goes like:
	```sql
		Select concat ('h', 'e', 'y');
	```
* The result are the chars concatenated, originating the string.
* Working with real data, it helps us to save time. the function CONCAT combines data from diferent columns in the same line, and concatenate them.
* the data to be concatenated must be inside of a set of parenthesis and separated by a comma.
* `concat (one_column, another_column);`
* `select concat (author_fname,' ', author_lname) from books;` - allows us to know the full name of the author, with a space separating the first name from the last name
* the issue above is that mysql is going to take the things between () as the name of the column. to solve that issue we do the follow:
* `select concat (author_fname,' ', author_lname) as author  from books; - this is going to display the name of the table as author.`
* **CONCAT_WS** allows us to concatenate with a separator. the syntax is:
* `select concat ('!', column1, column2)`
* where the exlamation point is the separator chosen by the user, and it is going to be used to separate each data from each column. always in between.
	

### 2. Substring -- Work with different parts of strings. it takes a single larger string and returns a smaller part of that string.
* `select substring ('Hello World', 1, 4)` -- is gonna return the first 4 chars of the whole string, starting counting at 1, and forward;
* `select substring ('Hello World', 7)` -- is gonna give us the first seven chars, forward.
* `select substring ('Hello World', -3)` -- is gonna give us the first 3 chars, backwards, from the last towards the first.
* `select substring(title, 1, 10) as 'short title' from books;` -- displays the first 10 chars of the title (including the spaces), starting to count at one.
* substituting `substring()` by `substr()` also works.

 #### Notes:
* substrings and concats can be combined.
* `select concat(substr(title, 1, 10), '...')as short_title from books;` - the substr() is inside the concat.
* the inner most is going to be evaluated first.
* `select concat(substring(author_fname, 1, 1),'.', substr(author_lname, 1, 1), '.') as initials from books;`

### 3. Replace -- replace parts of the strings
* `select replace ('hello world', 'hell', '%$#@');`
* the first arg is the sring we're working with, the second is the part of the string to be replaced, the third is the substitute of the string to be replaced.
* Important to notice that the capitalization matters, otherwise, the replacement is not gonna be done. Other examples:
* `select replace (title, ' ', '-') from books;`

### 4. Reverse -- Straightforward, it reverses a string.
* `select reverse ('chicken nuggets');`
* `select concat(author_fname, reverse(author_fname)) from books;` -- this turn the names into palindromes.

### 5. Char lenght - tells us the lenght of a string.
* `select char_lenght('hey!')`

### 6. Upper(), Lower() -- transform the string to upper and lowercase.
* upper("hello");
* lower('hello');
* `select concat ('I LOVE ', upper(title), ' !!!') from books;`


	



