### 1. What is Database?
A database is an organized collection of data, stored and retrieved digitally from a remote or local computer system. Databases can be vast 
and complex, and such databases are developed using fixed design and modeling approaches.
### 2. What is DBMS?
DBMS stands for Database Management System. DBMS is a system software responsible for the creation, retrieval, updation, and 
management of the database. It ensures that our data is consistent, organized, and is easily accessible by serving as an inte rface between 
the database and its end-users or application software.
### 3. What is RDBMS? How is it different from DBMS?
RDBMS stands for Relational Database Management System. The key difference here, compared to DBMS, is that RDBMS stores data in the 
form of a collection of tables, and relations can be defined between the common fields of these tables. Most modern database 
management systems like MySQL, Microsoft SQL Server, Oracle, IBM DB2, and Amazon Redshift are based on RDBMS.
### 4. What is SQL?
SQL stands for Structured Query Language. It is the standard language for relational database management systems. It is especially useful 
in handling organized data comprised of entities (variables) and relations between different entities of the data.
### 5. What is the difference between SQL and MySQL?
SQL is a standard language for retrieving and manipulating structured databases. On the contrary, MySQL is a relational database 
management system, like SQL Server, Oracle or IBM DB2, that is used to manage SQL databases.
### 6. What are Tables and Fields?
A table is an organized collection of data stored in the form of rows and columns. Columns can be categorized as vertical and rows as 
horizontal. The columns in a table are called fields while the rows can be referred to as records.
### 7. What are Constraints in SQL?
Constraints are used to specify the rules concerning data in the table. It can be applied for single or multiple fields in an SQL table during 
the creation of the table or after creating using the ALTER TABLE command. The constraints are:
- **NOT NULL** - Restricts NULL value from being inserted into a column.
- **CHECK** - Verifies that all values in a field satisfy a condition.
- **DEFAULT** - Automatically assigns a default value if no value has been specified for the field.
- **UNIQUE** - Ensures unique values to be inserted into the field.
- **INDEX** - Indexes a field providing faster retrieval of records.
- **PRIMARY KEY** - Uniquely identifies each record in a table.
- **FOREIGN KEY** - Ensures referential integrity for a record in another table.

### 8. What is a Primary Key?
The PRIMARY KEY constraint uniquely identifies each row in a table. It must contain UNIQUE values and has an implicit NOT NULL 
constraint.
A table in SQL is strictly restricted to have one and only one primary key, which is comprised of single or multiple fields (columns).

<img width="725" alt="image" src="https://user-images.githubusercontent.com/106428320/195978010-287f7f3b-4fd5-43b8-8ec0-478f9aef0ca4.png">


### 9. What is a UNIQUE constraint?

A UNIQUE constraint ensures that all values in a column are different. This provides uniqueness for the column(s) and helps identify each 
row uniquely. Unlike primary key, there can be multiple unique constraints defined per table. The code syntax for UNIQUE is quite similar to 
that of PRIMARY KEY and can be used interchangeably.

<img width="718" alt="image" src="https://user-images.githubusercontent.com/106428320/195978059-5ef1a793-d5f5-46c8-9346-4979c7c247cb.png">

### 10. What is a Foreign Key?

A FOREIGN KEY comprises of single or collection of fields in a table that essentially refers to the PRIMARY KEY in another table. Foreign key 
constraint ensures referential integrity in the relation between two tables.
The table with the foreign key constraint is labeled as the child table, and the table containing the candidate key is labeled as the 
referenced or parent table.

<img width="770" alt="image" src="https://user-images.githubusercontent.com/106428320/195978373-f6d87581-538a-48f0-9234-277d3969c657.png">

### 11. What is a Join? List its different types.

The SQL Join clause is used to combine records (rows) from two or more tables in a SQL database based on a related column between the 
two.

<img width="501" alt="image" src="https://user-images.githubusercontent.com/106428320/195978394-257bb2df-e0f7-4b33-8306-81d5c7bf70fa.png">

### There are four different types of JOINs in SQL:
- **(INNER) JOIN**: Retrieves records that have matching values in both tables involved in the join. This is the widely used join for queries.
    ```
    SELECT *
    FROM Table_A
    JOIN Table_B;
    
    SELECT *
    FROM Table_A
    INNER JOIN Table_B;
    ```
- **LEFT (OUTER) JOIN**: Retrieves all the records/rows from the left and the matched records/rows from the right table.
   ```
   SELECT *
   FROM Table_A A
   LEFT JOIN Table_B B
   ON A.col = B.col;
   ```
- **RIGHT (OUTER) JOIN**: Retrieves all the records/rows from the right and the matched records/rows from the left table.
   ```
   SELECT *
   FROM Table_A A
   RIGHT JOIN Table_B B
   ON A.col = B.col;
    ```
- **FULL (OUTER) JOIN**: Retrieves all the records where there is a match in either the left or right table.
    ```
    SELECT *
    FROM Table_A A
    FULL JOIN Table_B B
    ON A.col = B.col;
    ```
    
### 12. What is a Self-Join?
A self JOIN is a case of regular join where a table is joined to itself based on some relation between its own column(s). Self -join uses the 
INNER JOIN or LEFT JOIN clause and a table alias is used to assign different names to the table within the query.

<img width="717" alt="image" src="https://user-images.githubusercontent.com/106428320/195978715-1964dd9b-5ea0-499c-8d1f-1f8cc147de97.png">

### 13. What is a Cross-Join?
Cross join can be defined as a cartesian product of the two tables included in the join. The table after join contains the same number of 
rows as in the cross-product of the number of rows in the two tables. If a WHERE clause is used in cross join then the query will work like an 
INNER JOIN.

 <img width="471" alt="image" src="https://user-images.githubusercontent.com/106428320/195978742-d0371b71-8874-46b9-b27b-b088589a093a.png">
 
 <img width="794" alt="image" src="https://user-images.githubusercontent.com/106428320/195978790-bf1a530e-c82c-475d-aea8-de86ef1c0789.png">


### 14. What is an Index? Explain its different types.
A database index is a data structure that provides a quick lookup of data in a column or columns of a table. It enhances the speed of 
operations accessing data from a database table at the cost of additional writes and memory to maintain the index data structure.
  ```
  CREATE INDEX index_name /* Create Index */
  ON table_name (column_1, column_2);
  DROP INDEX index_name; /* Drop Index */
  ```

  There are different types of indexes that can be created for different purposes:
  - Unique and Non-Unique Index: 
    Unique indexes are indexes that help maintain data integrity by ensuring that no two rows of data in a table have identical key values. Once 
    a unique index has been defined for a table, uniqueness is enforced whenever keys are added or changed within the index.  
    ```
    CREATE UNIQUE INDEX myIndex
    ON students (enroll_no);
    ``` 
    Non-unique indexes, on the other hand, are not used to enforce constraints on the tables with which they are associated. Instead, 
    non-unique indexes are used solely to improve query performance by maintaining a sorted order of data values that are used frequently.
    
  - Clustered and Non-Clustered Index:
   
    Clustered indexes are indexes whose order of the rows in the database corresponds to the order of the rows in the index. This is why only 
    one clustered index can exist in a given table, whereas, multiple non-clustered indexes can exist in the table.
    
    The only difference between clustered and non-clustered indexes is that the database manager attempts to keep the data in the database 
    in the same order as the corresponding keys appear in the clustered index.
    
    Clustering indexes can improve the performance of most query operations because they provide a linear-access path to data stored in the 
    database.

### 15. What is the difference between Clustered and Non-clustered index?
As explained above, the differences can be broken down into three small factors -
- Clustered index modifies the way records are stored in a database based on the indexed column. A non-clustered index creates a separate 
entity within the table which references the original table.
- Clustered index is used for easy and speedy retrieval of data from the database, whereas, fetching records from the non-clustered index is 
relatively slower.
- In SQL, a table can have a single clustered index whereas it can have multiple non-clustered indexes.
### 16. What is Data Integrity?
Data Integrity is the assurance of accuracy and consistency of data over its entire life-cycle and is a critical aspect of the design, 
implementation, and usage of any system which stores, processes, or retrieves data. It also defines integrity constraints to enforce business 
rules on the data when it is entered into an application or a database.
### 17. What is a Query?
A query is a request for data or information from a database table or combination of tables. A database query can be either a select query 
or an action query.

```
SELECT fname, lname   /* select query */
FROM myDb.students
WHERE student_id = 1;
UPDATE myDB.students   /* action query */
SET fname = 'Captain', lname = 'America'
WHERE student_id = 1;
```
### 18. What is a Subquery? What are its types?
A subquery is a query within another query, also known as a nested query or inner query. It is used to restrict or enhance the data to be 
queried by the main query, thus restricting or enhancing the output of the main query respectively. For example, here we fetch the contact 
information for students who have enrolled for the maths subject:

<img width="451" alt="image" src="https://user-images.githubusercontent.com/106428320/195978919-5299a4f9-19aa-4bfb-97c3-ca10632b7984.png">

There are two types of subquery - Correlated and Non-Correlated.
- A correlated subquery cannot be considered as an independent query, but it can refer to the column in a table listed in the FROM of the 
main query.
- A non-correlated subquery can be considered as an independent query and the output of the subquery is substituted in the main query
### 19. What is the SELECT statement?
SELECT operator in SQL is used to select data from a database. The data returned is stored in a result table, called the result-set.

<img width="323" alt="image" src="https://user-images.githubusercontent.com/106428320/195982686-b4fbba1a-7357-4594-8a6c-8c543f8f0c39.png">

### 20. What are some common clauses used with SELECT query in SQL?
Some common SQL clauses used in conjuction with a SELECT query are as follows:
- **WHERE** clause in SQL is used to filter records that are necessary, based on specific conditions.
- **ORDER BY** clause in SQL is used to sort the records based on some field(s) in ascending (ASC) or descending order (DESC).
```
SELECT *
FROM myDB.students
WHERE graduation_year = 2019
ORDER BY studentID DESC;
```

- **GROUP BY** clause in SQL is used to group records with identical data and can be used in conjunction with some aggregation functions to 
produce summarized results from the database.
- **HAVING clause** in SQL is used to filter records in combination with the GROUP BY clause. It is different from WHERE, since the WHERE 
clause cannot filter aggregated records.
```
SELECT COUNT(studentId), country
FROM myDB.students
WHERE country != "INDIA"
GROUP BY country
HAVING COUNT(studentID) > 5;
```

### 21. What are UNION, MINUS and INTERSECT commands?
The **UNION** operator combines and returns the result-set retrieved by two or more SELECT statements.
The **MINUS** operator in SQL is used to remove duplicates from the result-set obtained by the second SELECT query from the result-set 
obtained by the first SELECT query and then return the filtered results from the first. 
The **INTERSECT** clause in SQL combines the result-set fetched by the two SELECT statements where records from one match the other and 
then returns this intersection of result-sets.
###### Certain conditions need to be met before executing either of the above statements in SQL -
- Each SELECT statement within the clause must have the same number of columns
- The columns must also have similar data types
- The columns in each SELECT statement should necessarily have the same order

<img width="701" alt="image" src="https://user-images.githubusercontent.com/106428320/195983237-d871e1ba-56a0-44c8-93f0-ea11bad14570.png">

### 22. What is Cursor? How to use a Cursor?
A database cursor is a control structure that allows for the traversal of records in a database. Cursors, in addition, facilitates processing after 
traversal, such as retrieval, addition, and deletion of database records. They can be viewed as a pointer to one row in a set of rows.
###### Working with SQL Cursor:
1. **DECLARE** a cursor after any variable declaration. The cursor declaration must always be associated with a SELECT Statement.
2. Open cursor to initialize the result set. The **OPEN** statement must be called before fetching rows from the result set.
3. **FETCH** statement to retrieve and move to the next row in the result set.
4. Call the **CLOSE** statement to deactivate the cursor.
5. Finally use the **DEALLOCATE** statement to delete the cursor definition and release the associated resources.

<img width="656" alt="image" src="https://user-images.githubusercontent.com/106428320/195983458-8c11f3d4-26a1-4329-baf6-02a4851fafa5.png">

### 23. What are Entities and Relationships?
**Entity**: An entity can be a real-world object, either tangible or intangible, that can be easily identifiable. For example, in a college database, 
students, professors, workers, departments, and projects can be referred to as entities. Each entity has some associated properties that 
provide it an identity.
**Relationships**: Relations or links between entities that have something to do with each other. For example - The employee's table in a 
company's database can be associated with the salary table in the same database.

<img width="526" alt="image" src="https://user-images.githubusercontent.com/106428320/195983560-15b9cc5c-e45e-443f-84e8-cdb4ef6ecb6c.png">

### 24. List the different types of relationships in SQL.
- One-to-One - This can be defined as the relationship between two tables where each record in one table is associated with the maximum 
of one record in the other table.
- One-to-Many & Many-to-One - This is the most commonly used relationship where a record in a table is associated with multiple records 
in the other table.
- Many-to-Many - This is used in cases when multiple instances on both sides are needed for defining a relationship.
- Self-Referencing Relationships - This is used when a table needs to define a relationship with itself.

### 25. What is an Alias in SQL?
An alias is a feature of SQL that is supported by most, if not all, RDBMSs. It is a temporary name assigned to the table or table column for 
the purpose of a particular SQL query. In addition, aliasing can be employed as an obfuscation technique to secure the real names of 
database fields. A table alias is also called a correlation name.

An alias is represented explicitly by the AS keyword but in some cases, the same can be performed without it as well. Nevertheless, using 
the AS keyword is always a good practice.

### 26. What is a View?
A view in SQL is a virtual table based on the result-set of an SQL statement. A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.

<img width="519" alt="image" src="https://user-images.githubusercontent.com/106428320/195983764-d9c7809e-2458-4b62-96dc-1b82e1c77233.png">

### 27. What is Normalization?
Normalization represents the way of organizing structured data in the database efficiently. It includes the creation of tables, establishing 
relationships between them, and defining rules for those relationships. Inconsistency and redundancy can be kept in check based on these 
rules, hence, adding flexibility to the database.
### 28. What is Denormalization?
Denormalization is the inverse process of normalization, where the normalized schema is converted into a schema that has redundant 
information. The performance is improved by using redundancy and keeping the redundant data consistent. The reason for performing 
denormalization is the overheads produced in the query processor by an over-normalized structure.
### 29. What are the various forms of Normalization?
Normal Forms are used to eliminate or reduce redundancy in database tables. The different forms are as follows:
- First Normal Form:
A relation is in first normal form if every attribute in that relation is a single-valued attribute. If a relation contains a composite or multivalued attribute, it violates the first normal form. Let's consider the following students table. Each student in the table, has a name, his/her 
address, and the books they issued from the public library -

<img width="618" alt="image" src="https://user-images.githubusercontent.com/106428320/195983890-336f8899-bcec-490b-963e-b5fe1d4a60ee.png">

As we can observe, the Books Issued field has more than one value per record, and to convert it into 1NF, this has to be resolved into 
separate individual records for each book issued. Check the following table in 1NF form -

<img width="601" alt="image" src="https://user-images.githubusercontent.com/106428320/195983935-1865bb93-4d18-4660-aef1-5ee0f05b6ad1.png">

- Second Normal Form:

A relation is in second normal form if it satisfies the conditions for the first normal form and does not contain any partial dependency. A 
relation in 2NF has **no partial dependency**, i.e., it has no non-prime attribute that depends on any proper subset of any candidate key of 
the table. Often, specifying a single column Primary Key is the solution to the problem. Examples -

**Example 1** - Consider the above example. As we can observe, the Students Table in the 1NF form has a candidate key in the form of 
[Student, Address] that can uniquely identify all records in the table. The field Books Issued (non-prime attribute) depends partially on the 
Student field. Hence, the table is not in 2NF. To convert it into the 2nd Normal Form, we will partition the tables into two while specifying a 
new **Primary Key** attribute to identify the individual records in the Students table. The **Foreign Key** constraint will be set on the other table 
to ensure referential integrity.

<img width="468" alt="image" src="https://user-images.githubusercontent.com/106428320/195984016-de55e46c-4954-4fe2-838f-dbe12afac97a.png">

<img width="392" alt="image" src="https://user-images.githubusercontent.com/106428320/195984032-05b528e0-420a-4082-bebd-b3ef4af45b86.png">

**Example 2** - Consider the following dependencies in relation to R(W,X,Y,Z)

<img width="399" alt="image" src="https://user-images.githubusercontent.com/106428320/195984084-dd192821-6f8e-4dfd-ae13-cbc417f8abf4.png">

Here, WX is the only candidate key and there is no partial dependency, i.e., any proper subset of WX doesn’t determine any non-prime 
attribute in the relation.

- Third Normal Form

A relation is said to be in the third normal form, if it satisfies the conditions for the second normal form and there is no transitive 
**dependency** between the non-prime attributes, i.e., all non-prime attributes are determined only by the candidate keys of the relation and 
not by any other non-prime attribute.

**Example 1** - Consider the Students Table in the above example. As we can observe, the Students Table in the 2NF form has a single 
candidate key Student_ID (primary key) that can uniquely identify all records in the table. The field Salutation (non-prime attribute), 
however, depends on the Student Field rather than the candidate key. Hence, the table is not in 3NF. To convert it into the 3rd Normal 
Form, we will once again partition the tables into two while specifying a new Foreign Key constraint to identify the salutations for 
individual records in the Students table. The Primary Key constraint for the same will be set on the Salutations table to identify each 
record uniquely.

<img width="547" alt="image" src="https://user-images.githubusercontent.com/106428320/195984231-c56b0135-da5a-4774-8ca6-74ad30601796.png">

<img width="404" alt="image" src="https://user-images.githubusercontent.com/106428320/195984259-d5b646e2-d1ff-4892-82c2-a5e3fa8413eb.png">

**Example 2** - Consider the following dependencies in relation to R(P,Q,R,S,T)
```
P -> QR [P together determine C]
RS -> T [B and C together determine D]
Q -> S
T -> P
```

For the above relation to exist in 3NF, all possible candidate keys in the above relation should be {P, RS, QR, T}.
- Boyce-Codd Normal Form

A relation is in Boyce-Codd Normal Form if satisfies the conditions for third normal form and for every functional dependency, Left-HandSide is super key. In other words, a relation in BCNF has non-trivial functional dependencies in form X –> Y, such that X is always a super 
key. For example - In the above example, Student_ID serves as the sole unique identifier for the Students Table and Salutation_ID for the 
Salutations Table, thus these tables exist in BCNF. The same cannot be said for the Books Table and there can be several books with 
common Book Names and the same Student_ID.

### 30. What are the TRUNCATE, DELETE and DROP statements?
**DELETE** statement is used to delete rows from a table.

```
DELETE FROM Candidates
WHERE CandidateId > 1000;
```

**TRUNCATE** command is used to delete all the rows from the table and free the space containing the table.

`TRUNCATE TABLE Candidates;`

**DROP** command is used to remove an object from the database. If you drop a table, all the rows in the table are deleted and the table 
structure is removed from the database.

`DROP TABLE Candidates;`

### 31. What is the difference between DROP and TRUNCATE statements?
If a table is dropped, all things associated with the tables are dropped as well. This includes - the relationships defined on the table with 
other tables, the integrity checks and constraints, access privileges and other grants that the table has. To create and use the table again in 
its original form, all these relations, checks, constraints, privileges and relationships need to be redefined. However, if a table is truncated, 
none of the above problems exist and the table retains its original structure.
### 32. What is the difference between DELETE and TRUNCATE statements?

The **TRUNCATE** command is used to delete all the rows from the table and free the space containing the table.
The **DELETE** command deletes only the rows from the table based on the condition given in the where clause or deletes all the rows from 
the table if no condition is specified. But it does not free the space containing the table.

### 33. What are Aggregate and Scalar functions?
An aggregate function performs operations on a collection of values to return a single scalar value. Aggregate functions are often used 
with the GROUP BY and HAVING clauses of the SELECT statement. Following are the widely used SQL aggregate functions:
- **AVG()** - Calculates the mean of a collection of values.
- **COUNT()** - Counts the total number of records in a specific table or view.
- **MIN()** - Calculates the minimum of a collection of values.
- **MAX()** - Calculates the maximum of a collection of values.
- **SUM()** - Calculates the sum of a collection of values.
- **FIRST()** - Fetches the first element in a collection of values.
- **LAST()** - Fetches the last element in a collection of values.

###### Note: All aggregate functions described above ignore NULL values except for the COUNT function.

A scalar function returns a single value based on the input value. Following are the widely used SQL scalar functions:

- **LEN()** - Calculates the total length of the given field (column).
- **UCASE()** - Converts a collection of string values to uppercase characters.
- **LCASE()** - Converts a collection of string values to lowercase characters.
- **MID()** - Extracts substrings from a collection of string values in a table.
- **CONCAT()** - Concatenates two or more strings.
- **RAND()** - Generates a random collection of numbers of a given length.
- **ROUND()** - Calculates the round-off integer value for a numeric field (or decimal point values).
- **NOW()** - Returns the current date & time.
- **FORMAT()** - Sets the format to display a collection of values.

### 34. What is User-defined function? What are its various types?
The user-defined functions in SQL are like functions in any other programming language that accept parameters, perform complex 
calculations, and return a value. They are written to use the logic repetitively whenever required. There are two types of SQL user-defined 
functions:
- Scalar Function: As explained earlier, user-defined scalar functions return a single scalar value.
- Table-Valued Functions: User-defined table-valued functions return a table as output.
- **Inline**: returns a table data type based on a single SELECT statement.
- **Multi-statement**: returns a tabular result-set but, unlike inline, multiple SELECT statements can be used inside the function body.
### 35. What is OLTP?
OLTP stands for Online Transaction Processing, is a class of software applications capable of supporting transaction-oriented programs. An 
essential attribute of an OLTP system is its ability to maintain concurrency. To avoid single points of failure, OLTP systems are often 
decentralized. These systems are usually designed for a large number of users who conduct short transactions. Database queries are usually 
simple, require sub-second response times, and return relatively few records. 

### 36. What are the differences between OLTP and OLAP?
OLTP stands for Online Transaction Processing, is a class of software applications capable of supporting transaction-oriented programs. An important attribute of an OLTP system is its ability to maintain concurrency. OLTP systems often follow a decentralized architecture to avoid single points of failure. These systems are generally designed for a large audience of end-users who conduct short transactions. Queries involved in such databases are generally simple, need fast response times, and return relatively few records. A number of transactions per second acts as an effective measure for such systems.

OLAP stands for Online Analytical Processing, a class of software programs that are characterized by the relatively low frequency of online transactions. Queries are often too complex and involve a bunch of aggregations. For OLAP systems, the effectiveness measure relies highly on response time. Such systems are widely used for data mining or maintaining aggregated, historical data, usually in multi-dimensional schemas.

<img width="486" alt="image" src="https://user-images.githubusercontent.com/106428320/195984734-03be1133-bd00-4d20-a566-b9cfbbdcce68.png">

### 37. What is Collation? What are the different types of Collation Sensitivity?
Collation refers to a set of rules that determine how data is sorted and compared. Rules defining the correct character sequence are used to 
sort the character data. It incorporates options for specifying case sensitivity, accent marks, kana character types, and character width. 
Below are the different types of collation sensitivity:
- *Case sensitivity*: A and a are treated differently.
- *Accent sensitivity*: a and á are treated differently.
- *Kana sensitivity*: Japanese kana characters Hiragana and Katakana are treated differently.
- *Width sensitivity*: Same character represented in single-byte (half-width) and double-byte (full-width) are treated differently.
### 38. What is a Stored Procedure?
A stored procedure is a subroutine available to applications that access a relational database management system (RDBMS). Such 
procedures are stored in the database data dictionary. The sole disadvantage of stored procedure is that it can be executed nowhere 
except in the database and occupies more memory in the database server. It also provides a sense of security and functionality as users 
who can't access the data directly can be granted access via stored procedures.

```
DELIMITER $$
CREATE PROCEDURE FetchAllStudents()
BEGIN
SELECT * FROM myDB.students;
END $$
DELIMITER ;
```

### 39. What is a Recursive Stored Procedure?
A stored procedure that calls itself until a boundary condition is reached, is called a recursive stored procedure. This recursive function 
helps the programmers to deploy the same set of code several times as and when required. Some SQL programming languages limit the 
recursion depth to prevent an infinite loop of procedure calls from causing a stack overflow, which slows down the system and may lead to 
system crashes.

```
DELIMITER $$ /* Set a new delimiter => $$ */
CREATE PROCEDURE calctotal( /* Create the procedure */
 IN number INT, /* Set Input and Ouput variables */
 OUT total INT
) BEGIN
DECLARE score INT DEFAULT NULL; /* Set the default value => "score" */
SELECT awards FROM achievements /* Update "score" via SELECT query */
WHERE id = number INTO score;
IF score IS NULL THEN SET total = 0; /* Termination condition */
ELSE
CALL calctotal(number+1); /* Recursive call */
SET total = total + score; /* Action after recursion */
END IF;
END $$ /* End of procedure */
DELIMITER ; /* Reset the delimiter */

```

### 40. How to create empty tables with the same structure as another table?
Creating empty tables with the same structure can be done smartly by fetching the records of one table into a new table using the INTO 
operator while fixing a WHERE clause to be false for all records. Hence, SQL prepares the new table with a duplicate structure to accept the 
fetched records but since no records get fetched due to the WHERE clause in action, nothing is inserted into the new table.
```
SELECT * INTO Students_copy
FROM Students WHERE 1 = 2;
```
### 41. What is Pattern Matching in SQL?
SQL pattern matching provides for pattern search in data if you have no clue as to what that word should be. This kind of SQL query uses 
wildcards to match a string pattern, rather than writing the exact word. The LIKE operator is used in conjunction with SQL Wildcards to 
fetch the required information.
- Using the % wildcard to perform a simple search

The % wildcard matches zero or more characters of any type and can be used to define wildcards both before and after the pattern. Search 
a student in your database with first name beginning with the letter K:
```
SELECT *
FROM students
WHERE first_name LIKE 'K%'
```
- Omitting the patterns using the NOT keyword

Use the NOT keyword to select records that don't match the pattern. This query returns all students whose first name does not begin with 
K.

```
SELECT *
FROM students
WHERE first_name NOT LIKE 'K%'
```
- Matching a pattern anywhere using the % wildcard twice

Search for a student in the database where he/she has a K in his/her first name.

```
SELECT *
FROM students
WHERE first_name LIKE '%Q%'
```
- Using the _ wildcard to match pattern at a specific position

The _ wildcard matches exactly one character of any type. It can be used in conjunction with % wildcard. This query fetches all students with 
letter K at the third position in their first name.

```
SELECT *
FROM students
WHERE first_name LIKE '__K%'
```

- Matching patterns for a specific length

The _ wildcard plays an important role as a limitation when it matches exactly one character. It limits the length and position of the 
matched results. For example -

```
SELECT * /* Matches first names with three or more letters */
FROM students
WHERE first_name LIKE '___%'
SELECT * /* Matches first names with exactly four characters */
FROM students
WHERE first_name LIKE '____'
```











