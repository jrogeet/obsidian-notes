z#### Queries with constraints

|                     |                                                      |                               |
| ------------------- | ---------------------------------------------------- | ----------------------------- |
| Operator            | Condition                                            | SQL Example                   |
| =, !=, < <=, >, >=  | Standard numerical operators                         | col_name != 4                 |
| BETWEEN … AND …     | Number is within range of two values (inclusive)     | col_name BETWEEN 1.5 AND 10.5 |
| NOT BETWEEN … AND … | Number is not within range of two values (inclusive) | col_name NOT BETWEEN 1 AND 10 |
| IN (…)              | Number exists in a list                              | col_name IN (2, 4, 6)         |
| NOT IN (…)          | Number does not exist in a list                      | col_name NOT IN (1, 3, 5)     |

|            |                                                                                                       |                                                                         |
| ---------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Operator   | Condition                                                                                             | Example                                                                 |
| =          | Case sensitive exact string comparison (_notice the single equals_)                                   | col_name = "abc"                                                        |
| != or <>   | Case sensitive exact string inequality comparison                                                     | col_name != "abcd"                                                      |
| LIKE       | Case insensitive exact string comparison                                                              | col_name LIKE "ABC"                                                     |
| NOT LIKE   | Case insensitive exact string inequality comparison                                                   | col_name NOT LIKE "ABCD"                                                |
| %          | Used anywhere in a string to match a sequence of zero or more characters (only with LIKE or NOT LIKE) | col_name LIKE "%AT%"  <br>(matches "AT", "ATTIC", "CAT" or even "BATS") |
| _          | Used anywhere in a string to match a single character (only with LIKE or NOT LIKE)                    | col_name LIKE "AN_"  <br>(matches "AND", but not "AN")                  |
| IN (…)     | String exists in a list                                                                               | col_name IN ("A", "B", "C")                                             |
| NOT IN (…) | String does not exist in a list                                                                       | col_name NOT IN ("D", "E", "F")                                         |



>[!info] Database
> - Create Database:
>```SQL
>CREATE DATABASE myDB;
>```
> - Use Database:
> ```sql
> USE myDB;
> ```
> - Drop Database:
> ```sql
> DROP DATABASE myDB;
> ```
>> [!TIP] Read-Only Database
>> ```sql
>> ALTER DATABASE myDB READ ONLY = 1;
>> // 1 = ENABLE
>> // 0 = DISABLE
>> ```
>> - CANT BE MODIFIED
>> - CAN STILL BE ACCESSED
>
>
>


> [!INFO] TABLES
> ```sql
> CREATE TABLE employees (
> 	employee_id INT,
> 	first_name VARCHAR(50),
> 	last_name VARCHAR(50).
> 	hourly_pay DECIMAL(5, 2),
> 	hiredate DATE
> );
> ```
> ```sql
> CREATE TABLE Users(
> 	id INT PRIMARY KEY AUTO_INCREMENT,
> 	email VARCHAR(255) NOT NULL UNIQUE,
> 	bio TEXT,
> 	country VARCHAR(2)
> );
> ```
> 
> - SELECT TABLE
> ```sql
> SELECT * FROM employees
> ```
>  - RENAME TABLE
>```sql
>RENAME TABLE employees TO workers
>```

>[!INFO] Insert
>```sql
>INSERT INTO Users (email, bio, country)
>VALUES (
>	'hello@world.com',
>	'i love strangers!',
>	'US'
>);
>```
>```SQL
>INSERT INTO Users (email, bio, country)
>VALUES
>	('hello@world.com', 'foo', 'US')
>	('hola@munda.com', 'bar', 'MX'),
>	('bounjour@monde.com', 'baz', 'FR');
>```

> [!INFO] Read data
> ```sql
> SELECT * FROM Users;
> 
> SELECT email, id FROM Users;
> ```
> 

> [!info] FILTERING and SOTRING Query results
> - __DISTINCT__ - Removes duplicate `rows`
> ```sql
> SELECT DISTINCT Names FROM table;
> ```
> - __ORDER BY__ - Sorts `columns` __Alpha__-___Numerically___ based on the `column`'s value.
> ```sql
> SELECT column, another_column
> FROM mytable
> WHERE condition(s)
> ORDER BY column ASC/DESC;
> ```
> - __LIMIT__ - Reduce __number of `rows`__ to return
> - ___OFFSET___ - Specify __where to begin counting__ the number of `rows` from
> ```sql
> SELECT column
> FROM mytable
> LIMIT num_limit OFFSET num_offset;
> // EXAMPLE: Shows 5 results STARTING from 5:
> LIMIT 5 OFFSET 5
> ```

> [!tip] INDEX
> Retrieve data quickly,
> - Finds keyword without scanning the whole dataset
> 	- Slower write and Addition memory
> ```sql
> CREATE INDEX email_index ON Users(email);
> ```
> Reference:
> ```sql
> SELECT email, id, country FROM Users
> 
>WHERE country = 'US'
>AND email LIKE 'h%'
>
>ORDER BY id DESC
>LIMIT 2;
> ```


> [!ABSTRACT] RELATIONS
> ```sql
> CREATE TABLE Rooms (
> 	id INT AUTO_INCREMENT, // PRIMARY KEY
> 	street VARCHAR(255),
> 	owner_id INT NOT NULL, // FOREIGN KEY (from another table)
> 	PRIMARY KEY (id),
> 	FOREIGN KEY (owner_id) REFERENCES Users(id)
> )
> ```
> 
> ```sql
> INSERT INTO Rooms (owner_id, street)
> VALUES
> 	(1, 'san diego sailboat'),
> 	(1, 'nantucket cottage'),
> 	(1, 'vail cabin'),
> 	(1, 'sf cardboard box');
> ```
> 
> - __INNER JOIN__:
> ![[Pasted image 20240403105820.png]]
> ```sql
> SELECT * FROM Users
> LEFT JOIN Rooms
> ON Rooms.owner_id = Users.id;
> ```
> - __LEFT JOIN__:
> ![[Pasted image 20240403105930.png]]
> ```sql
> SELECT * FROM Users
> LEFT JOIN RoomsON Rooms.owner_id = Users.id;
> ```
```
```




> [!info] __MULTI-TABLE__ queries with `JOINS`
> - __INNER JOIN__ - Matches `rows` from _First Table_ and ___Second Table___  with the same __key__
> 	- __key__ is defined by `ON` constraint
> ```sql
> INNER JOIN another_table
> 	ON mytable.id = another_table.id
> ```
>> [!example]
>> ![[Pasted image 20240402213138.png]]
>> - Find the domestic and international sales for each movie
>> ```sql
>> SELECT * FROM movies
>> INNER JOIN Boxoffice
>> 	ON Id = Movie_id;
>> ```
>> - Show the sales numbers for each movie that did better internationally rather than domestically
>> ```sql
>> SELECT * FROM movies
>>INNER JOIN Boxoffice
>>    ON Id = Movie_id
>>WHERE domestic_sales < international_sales;
>> ```
>> -  List all the movies by their ratings in descending order
>> ```sql
>> SELECT * FROM movies
>> INNER JOIN Boxoffice
>> 	  ON Id = Movie_id
>> ORDER BY rating DESC ;
>> ```
>> - __LEFT JOIN__ - Includes `rows` from __A__ regardless of whether a `matching row` is found in ___B___.
>> ```sql
>> SELECT DISTINCT building FROM employees
>> LEFT JOIN buildings 
>> 	ON employees.building = buildings.building_name;
>> ```
>> - __RIGHT JOIN__ - Reversed of __left join__, keeps `rows` in ___B___ regardless of whether a `matching row` is found in __A__.
>> - __FULL JOIN__ - `Rows` from _BOTH TABLES_ are kept, regarless of whether a `matching row` exists in the _OTHER TABLE._
