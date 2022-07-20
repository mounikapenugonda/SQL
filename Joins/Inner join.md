Inner JOIN : It will give both the common rows present in the 2 or more tables.
             - Inner joins combine records from two tables whenever there are matching values in a field common to both tables

create table A : create table A((id integer , name varchar(20));
| ID | Name|
| -- | --|
|1|pankhu|
|1|bozo|
|2|Aathmika|
|3|kyo|
|3|pankhu|
|4|lee|
|5|bo young|
|6|bozo|
|6|kyo|

create table B : create table A((id integer , name varchar(20));
| ID | Name|
| -- | --|
|1|lee|
|2|bo young|
|2|pankhu|
|3|Aathmika|
|4|pankhu|
|5|bozo|
|15|bo young|
|19|kyo|
|25|lee|

How many rows will give as output  -- inner join on id : 

    Query for count : select count(*) from A inner join B on a.id = b.id ;
        Result : 8
        
    Query for rows/observations : select * from A inner join B on a.id = b.id ;
        Result :  
| id | name | id | name|
| -- | -- | -- | -- |
|1 |	bozo|	1|	lee|
|1	|pankhu |	1	|lee|
|2	|Aathmika	|2	|bo young|
|2	|Aathmika	|2	|pankhu|
|3	|pankhu	|3	|Aathmika|
|3	|kyo	|3|	Aathmika|
| 4	|lee	|4|	pankhu|
| 5	|bo young|	5|	bozo|


How many rows will give as output  -- inner join on name : 

    Query for count : select count(*) from A inner join B on a.name = b.name ;
        Result : 13
        
    Query for rows/observations : select * from A inner join B on a.name = b.name order by name asc ;
        Result : 
| id | name | id | name|
| -- | -- | -- | -- |
|2	|Aathmika|3	|Aathmika|
| 5	|bo young| 2	|bo young|
| 5	|bo young| 15	|bo young|
|6 |	bozo|	5 |	bozo|	
|1 |	bozo|	5 |	bozo|	
|6	|kyo	|19	|kyo	|
|3	|kyo	|19	|kyo	|
| 4	|lee | 1	|lee|
| 4	|lee | 25	|lee|
|3	|pankhu	|2	|pankhu	|
|1	|pankhu	|2	|pankhu	|
|3	|pankhu	|4	|pankhu	|
|1	|pankhu	|4	|pankhu	|
