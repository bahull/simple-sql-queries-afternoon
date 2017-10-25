<img src="https://devmounta.in/img/logowhiteblue.png" width="250" align="right">

# Project Summary

In this project we will be practicing inserting and querying data using SQL. We'll make use of a handy online tool called Chinook that we'll use to write SQL online. <a href="http://jxs.me/chinook-web/">Click me</a>

On the left are the Tables with their fields, the right is where we will be writing our queries, and the bottom is where we will see our results.  

Any new tables or records that we add into the database will be removed after you refresh the page.

Use [www.sqlteaching.com](http://www.sqlteaching.com/) or [sqlbolt.com](http://sqlbolt.com/) as resources for the missing keywords you'll need.

## Table - People

### Instructions
1. Create a table called Person that records a person's ID, Name, Age, Height ( in cm ), City, FavoriteColor. 
    * ID should be an auto-incrementing id/primary key - Use type: INTEGER PRIMARY KEY AUTOINCREMENT
    (  create table Person (
  id Integer Primary Key Autoincrementing,
    name NVarchar(100),
    age Integer,
    height Integer,
    city Nvarchar(100),
    favorite_color Nvarchar(40)
    
  ))
    
2. Add 5 different people into the Person database. 
    * Remember to not include the ID because it should auto-increment.
3. List all the people in the Person table by Height from tallest to shortest.
(Select *
From Person
Order by height Desc;)

4. List all the people in the Person table by Height from shortest to tallest.
(Select *
From Person
Order by height Asc;)

5. List all the people in the Person table by Age from oldest to youngest.
(Select*
From Person
Order by age Desc;)

6. List all the people in the Person table older than age 20.
(Select*
From Person
where age > 20;)

7. List all the people in the Person table that are exactly 18.
(Select *
From Person
where age = 18;)

8. List all the people in the Person table that are less than 20 and older than 30.
(Select *
From Person
where age < 20 Or age > 30;)

9. List all the people in the Person table that are not 27 (Use not equals).
(Select *
From Person
where age != 27;)

10. List all the people in the Person table where their favorite color is not red.
(Select *
From Person
where favorite_color != 'Red';)

11. List all the people in the Person table where their favorite color is not red and is not blue.
(Select *
From Person
where favorite_color != 'Red' And favorite_color !='Blue';)

12. List all the people in the Person table where their favorite color is orange or green.
(Select *
From Person
where favorite_color = 'orange' Or favorite_color ='green';)

13. List all the people in the Person table where their favorite color is orange, green or blue (use IN).
(Select *
From Person
where favorite_color In ('orange', 'green', 'blue');)

14. List all the people in the Person table where their favorite color is yellow or purple (use IN).
(Select *
From Person
where favorite_color In ('yellow', 'purple');)

### Solution

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>

```sql
CREATE TABLE Person ( ID INTEGER PRIMARY KEY AUTOINCREMENT, Name string, Age integer, Height integer, City string, FavoriteColor string );
```

</details>

<details>

<summary> <code> #2 </code> </summary>

```sql
INSERT INTO Person ( Name, Age, Height, City, FavoriteColor ) VALUES ( "First Last", 21, 182, "City", "Color" );
```

</details>

<details>

<summary> <code> #3 </code> </summary>

```sql
SELECT * FROM Person ORDER BY Height DESC;
```

</details>

<details>

<summary> <code> #4 </code> </summary>

```sql
SELECT * FROM Person ORDER BY Height ASC;
```

</details>

<details>

<summary> <code> #5 </code> </summary>

```sql
SELECT * FROM Person ORDER BY Age DESC;
```

</details>

<details>

<summary> <code> #6 </code> </summary>

```sql
SELECT * FROM Person WHERE Age > 20;
```

</details>

<details>

<summary> <code> #7 </code> </summary>

```sql
SELECT * FROM Person WHERE Age = 18;
```

</details>

<details>

<summary> <code> #8 </code> </summary>

```sql
SELECT * FROM Person WHERE Age < 20 OR Age > 30;
```

</details>

<details>

<summary> <code> #9 </code> </summary>

```sql
SELECT * FROM Person WHERE Age != 27;
```

</details>

<details>

<summary> <code> #10 </code> </summary>

```sql
SELECT * FROM Person WHERE FavoriteColor != "red";
```

</details>

<details>

<summary> <code> #11 </code> </summary>

```sql
SELECT * FROM Person WHERE FavoriteColor != "red" AND FavoriteColor != "blue";
```

</details>

<details>

<summary> <code> #12 </code> </summary>

```sql
SELECT * FROM Person WHERE FavoriteColor = "orange" OR FavoriteColor = "green";
```

</details>

<details>

<summary> <code> #13 </code> </summary>

```sql
SELECT * FROM Person WHERE FavoriteColor IN ( "orange", "green", "blue" );
```

</details>

<details>

<summary> <code> #14 </code> </summary>

```sql
SELECT * FROM Person WHERE FavoriteColor IN ( "yellow", "purple" )
```

</details>

</details>

## Table - Orders

### Instructions

1. Create a table called Orders that records: PersonID, ProductName, ProductPrice, Quantity.
(Create Table Orders (
  person_id Integer Primary key Autoincrement,
  product_name Nvarchar(40),
  product_price Integer,
  quantity Integer
);)

2. Add 5 Orders to the Orders table.
    * Make orders for at least two different people.
    * PersonID should be different for different people.
3. Select all the records from the Orders table.
(Select *
From Orders;)

4. Calculate the total number of products ordered.
(Select Sum(quantity)
From Orders;)

5. Calculate the total order price.
(Select Sum(product_price)
From Orders;)

6. Calculate the total order price by a single PersonID.
(Select Sum(product_price * quantity)
From Orders 
where person_id Like 'John';)


### Solution

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>

```sql
CREATE TABLE Orders ( PersonID integer, ProductName string, ProductPrice float, Quantity integer );
```

</details>

<details>

<summary> <code> #2 </code> </summary>

```sql
INSERT INTO Orders ( PersonID, ProductName, ProductPrice, Quantity ) VALUES ( 0, "Product", 12.50, 2 );
```

</details>

<details>

<summary> <code> #3 </code> </summary>

```sql
SELECT * FROM Orders;
```

</details>

<details>

<summary> <code> #4 </code> </summary>

```sql
SELECT SUM(Quantity) FROM Orders;
```

</details>

<details>

<summary> <code> #5 </code> </summary>

```sql
SELECT SUM(ProductPrice * Quantity) FROM Orders;
```

</details>

<details>

<summary> <code> #6 </code> </summary>

```sql
/* The value of PersonID depends on what IDs you used. Use a valid ID from your table */
SELECT SUM(ProductPrice * Quantity) FROM Orders WHERE PersonID = 0;
```

</details>

</details>

## Table - Artist

### Instructions

1. Add 3 new Artists to the Artist table. ( It's already created )
(Insert Into Artist (name)
Values ('Coldplay'),('Nickelback'), ('Linkin Park');)

2. Select 10 artists in reverse alphabetical order.
(Select *
From Artist 
Order by Name Desc
Limit 10;)

3. Select 5 artists in alphabetical order.
(Select *
From Artist 
Order by Name Asc
Limit 5;)

4. Select all artists that start with the word "Black".
(Select * 
from Artist
where name Like 'Black%';)

5. Select all artists that contain the word "Black".
(Select * 
from Artist
where name Like '%Black%';)

### Solution 

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>

```sql
INSERT INTO Artist ( Name ) VALUES ( 'artist name' );
```

</details>

<details>

<summary> <code> #2 </code> </summary>

```sql
SELECT * FROM Artist ORDER BY Name Desc LIMIT 10;
```

</details>

<details>

<summary> <code> #3 </code> </summary>

```sql
SELECT * FROM Artist ORDER BY Name ASC LIMIT 5;
```

</details>

<details>

<summary> <code> #4 </code> </summary>

```sql
SELECT * FROM Artist WHERE Name LIKE 'Black%';
```

</details>

<details>

<summary> <code> #5 </code> </summary>

```sql
SELECT * FROM Artist WHERE Name LIKE '%Black%';
```

</details>

</details>

## Table - Employee

### Instructions

1. List all Employee first and last names only that live in Calgary.
(Select FIRSTNAME , LASTNAME
from Employee
where City = 'Calgary';)

2. Find the first and last name and birthdate for the youngest employee.
(Select FIRSTNAME, LASTNAME, Min(BIRTHDATE)
from Employee;)

3. Find the first and last name and birthdate for the oldest employee.
(Select FIRSTNAME, LASTNAME, Max(BIRTHDATE)
from Employee;)

4. Find everyone that reports to Nancy Edwards (Use the ReportsTo column).
   * You will need to query the employee table to find the Id for Nancy Edwards
   (Select *
from Employee
Where ReportsTo = 2;)
   
5. Count how many people live in Lethbridge.
(Select *
from Employee
Where City = 'Lethbridge';)


### Solution

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>

```sql
SELECT FirstName, LastName FROM Employee WHERE City = "Calgary";
```

</details>

<details>

<summary> <code> #2 </code> </summary>

```sql
SELECT FirstName, LastName, Max(BirthDate) FROM Employee;
```

</details>

<details>

<summary> <code> #3 </code> </summary>

```sql
SELECT FirstName, LastName, Min(BirthDate) FROM Employee;
```

</details>

<details>

<summary> <code> #4 </code> </summary>

```sql
SELECT * FROM Employee WHERE ReportsTo = 2;
```

</details>

<details>

<summary> <code> #5 </code> </summary>

```sql
SELECT COUNT(*) FROM Employee WHERE City = "Lethbridge";
```

</details>

</details>

## Table - Invoice 

### Instructions

1. Count how many orders were made from the USA.
(Select count(*)
from Invoice
Where BillingCountry = 'USA';)

2. Find the largest order total amount.
(Select Max(total)
from Invoice;)

3. Find the smallest order total amount.
Select Min(total)
from Invoice;

4. Find all orders bigger than $5.
(Select *
from Invoice
Where Total > 5;)

5. Count how many orders were smaller than $5.
(Select count(*)
from Invoice
Where Total < 5;)

6. Count how many orders were in CA, TX, or AZ (use IN).
(Select count(*)
from Invoice
Where BillingState In ('CA', 'TX', 'AZ');)

7. Get the average total of the orders.
(Select Avg(Total)
from Invoice;
)

8. Get the total sum of the orders.
(Select Sum(Total)
from Invoice;
)


### Solution

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>

```sql
SELECT Count(*) FROM Invoice WHERE BillingCountry = 'USA';
```

</details>

<details>

<summary> <code> #2 </code> </summary>

```sql
SELECT Max(total) FROM Invoice;
```

</details>

<details>

<summary> <code> #3 </code> </summary>

```sql
SELECT Min(total) FROM Invoice;
```

</details>

<details>

<summary> <code> #4 </code> </summary>

```sql
SELECT * FROM Invoice WHERE Total > 5;
```

</details>

<details>

<summary> <code> #5 </code> </summary>

```sql
SELECT COUNT(*) FROM Invoice WHERE Total < 5;
```

</details>

<details>

<summary> <code> #6 </code> </summary>

```sql
SELECT Count(*) FROM Invoice WHERE BillingState in ('CA', 'TX', 'AZ');
```

</details>

<details>

<summary> <code> #7 </code> </summary>

```sql
SELECT AVG(Total) FROM Invoice;
```

</details>

<details>

<summary> <code> #8 </code> </summary>

```sql
SELECT SUM(Total) FROM Invoice;
```

</details>

</details>

## Contributions

If you see a problem or a typo, please fork, make the necessary changes, and create a pull request so we can review your changes and merge them into the master repo and branch.

## Copyright

© DevMountain LLC, 2017. Unauthorized use and/or duplication of this material without express and written permission from DevMountain, LLC is strictly prohibited. Excerpts and links may be used, provided that full and clear credit is given to DevMountain with appropriate and specific direction to the original content.

<p align="center">
<img src="https://devmounta.in/img/logowhiteblue.png" width="250">
</p>

