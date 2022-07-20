Inner JOIN : returns all rows from the left table, even if there are no matches in the right table. This means that if the ON clause matches 0 (zero) records in the
            right table; the join will still return a row in the result, but with NULL in each column from the right table.

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

How many rows will give as output  -- left join on id : 

    Query for count : select count(*) from A left join B on a.id = b.id ;
        Result : 10
        
    Query for rows/observations : select * from A left join B on A.id = b.id order by a.id asc;
        Result :  
| id | name | id | name|
| -- | -- | -- | -- |
|1	|pankhu |	1	|lee|
|1 |	bozo|	1|	lee|
|2	|Aathmika	|2	|bo young|
|2	|Aathmika	|2	|pankhu|
|3	|pankhu	|3	|Aathmika|
|3	|kyo	|3|	Aathmika|
| 4	|lee	|4|	pankhu|
| 5	|bo young|	5|	bozo|
| 6 | bozo | | null| null|
| 6 | kyo | | null| null|
