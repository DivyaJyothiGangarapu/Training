# SQL

### DATABASE

- database is a special software used to store data in a systematic format.
- cloud is a renting pc's it will rent systems only.it is better to rent because(high initial cost,rent room,AC for cooling,electric bill,maintainance,spares,generators)
- Disaster mgmt( servers should be in disaster prone areas,maintain backup)
- db lives in cloud

#### cloud storage providers

pcloud,dropbox,google drive,mega,just cloud

#### cloud providers

aws,ibm cloud, azure,salesforce,google cloud platform,alibaba cloud  
only provides service, we can install any softwares in it.

- amazon leads cloud platform.

### LINUX

- used as OS in cloud because (free,open source)

### Scaling

to increase the server load, adding cpu power,by vertical scaling

#### Vertical Scaling VS Horizontal scaling

vertical making PC power, increasing the power whereas horizontal is adding more no. of PCs  
upto some limit vertical is cheaper after that horizontal is better

#### Auto Scaling

At the time of more load(i.e big billion sales) , the load on server will be differ in different times(mrg,aftn,ngt) upscaling and downscaling will be done automatically.

#### disadvantages of auto scaling

DDos attacks hackers may increase the traffic and hack the server, to prevent it we have to divert the traffic ,by identifying which is human and which is robot by captcha,by IP address tracking the area

### Why database

it automatically load the data from harddisk to ram(frequently accesed data FAD) that saves the time,loading means the copying the files into RAM from hard disk.  
hard disk-bottle neck -limits the data.

- frequently asked it will have it in the ram
- querying becomes easy
- CRUD - easy
- Backups are inbuild
- Undo- easily( time limit)
- performance

### SQL VS NOSQL

- relational databases(mysql,pLSQL,postgre SQL,amazon RDS)
- Non- relational databases(noSQL)(mongo DB, redis,couchDB,cassandra(netflix),DynamoDB)

### why should it is imp to normalize the table

to avoid redundancy, storage, to prevent the anomalies issues (updating anomaly,insertion ,deletion), if in case of updating values in several rows, in middle it crashes,updation will be in middle.

### primary key rules

- unique, not null, only one in a table

#### inner join

Select query with INNER JOIN on multiple tables
SELECT column, another_table_column, …
FROM mytable
INNER JOIN another_table
ON mytable.id = another_table.id
WHERE condition(s)
ORDER BY column, … ASC/DESC
LIMIT num_limit OFFSET num_offset;

### inner join and outer join

the INNER JOIN we used last lesson might not be sufficient because the resulting table only contains data that belongs in both of the tables.

If the two tables have asymmetric data, which can easily happen when data is entered in different stages, then we would have to use a LEFT JOIN, RIGHT JOIN or FULL JOIN instead to ensure that the data you need is not left out of the results.
Like the INNER JOIN these three new joins have to specify which column to join the data on.
When joining table A to table B, a LEFT JOIN simply includes rows from A regardless of whether a matching row is found in B. The RIGHT JOIN is the same, but reversed, keeping rows in B regardless of whether a match is found in A. Finally, a FULL JOIN simply means that rows from both tables are kept, regardless of whether a matching row exists in the other table.

### 1nf

![alt text](<Screenshot 2024-06-11 115159.png>)

### 2nf

non key values should depend on entire combined primary key
it should be in 1 nf and 2 nf

### 3nf

there should be no dependency ,it will cause the updation anomaly i.e. one value will be updated and other will not update.
![alt text](<Screenshot 2024-06-11 150252.png>)

## aggregate function

SELECT AGG_FUNC(column_or_expression) AS aggregate_description, …
FROM mytable
WHERE constraint_expression
GROUP BY column;

- when we want to drill down one level deep then we use group by.

## order of query execution

cant be interchangable

SELECT DISTINCT column, AGG_FUNC(column_or_expression), …
FROM mytable
JOIN another_table
ON mytable.column = another_table.column
WHERE constraint_expression
GROUP BY column
HAVING constraint_expression
ORDER BY column ASC/DESC
LIMIT count OFFSET COUNT;

- 1. FROM and JOINs subsequences
- 2. WHERE
- 3. GROUP BY
- 4. HAVING
- 5. SELECT
- 6. DISTINCT
- 7. ORDER BY
- 8. LIMIT / OFFSET

### Insering rows

schema is what describes the structure of each table, and the datatypes that each column of the table can contain.

### SQL

SQL, or Structured Query Language query, manipulate, and transform data from a relational database.
Relational databases represents a collection of related (two-dimensional) tables.

#### SELECT

To retrieve data from a SQL database

```sql
SELECT column, another_column, …
FROM mytable;
```

![alt text](<Screenshot 2024-06-12 214506.png>)
![alt text](<Screenshot 2024-06-12 214718.png>)

#### Filtering and sorting Query results

- DISTINCT keyword will blindly remove duplicate rows,
- ORDER BY clause is specified, each row is sorted alpha-numerically based on the specified column's value.
- LIMIT will reduce the number of rows to return, and the optional OFFSET will specify where to begin counting the number rows from.

```sql
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC
LIMIT num_limit OFFSET num_offset;
```

### Database normalization

it minimizes duplicate data in any single table, and allows for data in the database to grow independently of each other

```sql
SELECT column, another_column, …
FROM mytable
INNER/LEFT/RIGHT/FULL JOIN another_table
    ON mytable.id = another_table.matching_id
WHERE condition(s)
ORDER BY column, … ASC/DESC
LIMIT num_limit OFFSET num_offset;
```

### NULL

where column is null/ not null

```sql
SELECT col_expression AS expr_description, …
FROM mytable;
```

### Aggregate functions

count(),min(),max(),avg(),sum()

- HAVING clause which is used specifically with the GROUP BY clause to allow us to filter grouped rows from the result set.

### Insertion

```sql
INSERT INTO mytable
(column, another_column, …)
VALUES (value_or_expr, another_value_or_expr, …),
      (value_or_expr_2, another_value_or_expr_2, …),
      …;
```

### Updating rows

```sql
UPDATE mytable
SET column = value_or_expr,
    other_column = another_value_or_expr,
    …
WHERE condition;
```

### Deleting rows

```sql
DELETE FROM mytable
WHERE condition;
```

### Creating tables

```aql
CREATE TABLE IF NOT EXISTS mytable (
    column DataType TableConstraint DEFAULT default_value,
    another_column DataType TableConstraint DEFAULT default_value,
    …
);
```

### Altering tables

```sql
ALTER TABLE mytable
ADD column DataType OptionalTableConstraint
    DEFAULT default_value;

ALTER TABLE mytable
DROP column_to_be_deleted;

ALTER TABLE mytable
RENAME TO new_table_name;

```

### Dropping tables

```sql
DROP TABLE IF EXISTS mytable;
```

### DATA TYPES

- INTEGER(whole numbers), BOOLEAN( 0 or 1 )
- FLOAT(3 decimal), DOUBLE(6 decimal), REAL(12)
- CHARACTER(num_chars)(M or F), VARCHAR(num_chars)(string or sentence with limit of letters), TEXT(paras without limit)
- DATE, DATETIME
- BLOB(binary data in images, computer data)

### Constraint

which limit what values can be inserted into that column. maintain data integrity(data correctness)

- PRIMARY KEY (unique, and each value can be used to identify a single row in this table.)
- AUTOINCREMENT
- UNIQUE
- NOT NULL
- CHECK (expression)
- FOREIGN KEY
  we can also join 2 tables without using foreign key.It is useful at the time of insertion and deletion
  if it is present in first table ,it checks and enters the data into second table and same as the deletion it is reverse process

#### INTEGER

Int(-2B,2B)
small int(-32k,32k)
big int(-9*10^8 , 9*10^8)

#### String

varchar
nvarchar(unicode"\UF12" for using other languages ,multiple unicode emojois)

```python
"😵‍💫".split()
```

Result: ["\U12","\U1233","\U424"]  
where varchar store it as 3 characters,where as nvarchar store it as 1

- varchar(max) = TEXT stores max

### Decimal

- decimal(exact)= less performance but stores the exact value of the decimal
  where decimal(10,2) it rounds the decimal values to 2 decimals
- float = high performance but it stores approx value but not the exact

### Boolean

### Functions

1. aggregate functions
2. string functions
3. mathematical functions
4. format functions

## string functions

- Len('string')
- left('string',no. of characters)
- right
- substring(start index,end index)
- upper(string)
- lower(string)
- Ltrim(string)= removes space from left side
- Ltrim(string,left most string)= SELECT LTRIM('123abc.' , '123.');= removes
- Rtrim(string)
- charIndex(str_to_be_search,str, start_index_for_searching)
- replace(str, str_to_be_replaced, new_str)
- concat(str1, str2)= combines to strings
- replicate()

```sql

--- String functions
--1. len
select Len('divya') as name_length
-- 2.left
select Left('divya jyothi',200) as lef
-- 3.right
select right('divya jyothi',2) as ri
-- 4.substring
select substring('divya jyothi',1,8) as ri
-- 5.upper
select upper('       divya') as name1
-- 6.lower
select lower('padmA')
-- 7.Ltim
select Ltrim('  Divjyo','  Dij') as trim1
-- 8.Rtrim
select Rtrim('Divjyo  ','  uyo  ') as trim1
-- 9.charindex
select charindex('l','welcome',3)
-- 10.replace
select replace('hitex','hi','hello')
-- 11.concat
select concat('hi ','hello')   --hi hello
-- 12.replicate
select replicate('fun friday',5)    --fun fridayfun fridayfun fridayfun fridayfun friday
-- 13.reverse
select reverse('fun friday')      --yadirf nuf

-- Mathematical functions
--1. Abs
select abs(-10)                --10
-- 2. Power
select power(2,4)              --16
-- 3. Round
select round(3.45659999996,2)       --3.46000000000
--4.ceiling
select ceiling(34.2)            --35
--5.floor
select floor(34.777)                --34
-- data functions
--1.Getdate
select getdate()                   --2024-06-13 12:50:28.563
--2. Dateadd
select dateadd day, 10 ,getdate()
--3. datediff
select datediff(day,2024-06-13 ,2024-06-17 )                  --164 if u want to give getdate() inside just put other in string
select datediff(HH,'2024-01-01 00:00:00',getdate())                --3949 if u press ctrl+space u can see the options that can be given
--4. format
select format(GETDATE(),'dd/MM/yyyy' )
--5.datepart(extract the part from the date)
select datepart(month,getdate())              --6
select datepart(day,getdate())              --13
```

```sql
select "Name" from employees
union
select "Name" from contractors;
```

##### union,union all, except, intersect

#### MultiJoins

```sql
select e.EmployeeID,ProjectName from employees e
inner join participations p
on e.EmployeeID=p.EmployeeID
inner join projects r
on p.ProjectID=r.ProjectID
```
