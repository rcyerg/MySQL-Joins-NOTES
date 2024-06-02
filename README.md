
# NOTES ON JOINS

#### ◆ INNER JOIN

- Returns rows when there is at least one match in both tables
- Avoid ambiguity by qualifying each column with table name
- Joins tables based on relationships
- Operators: '**=**' , '**>**', '**<**', '**<=**', '**>=**'

<img src=images/Inner_Join.PNG width=400/img>

##### **Syntax** 

- Implicit Syntax
  - SELECT t1.*, t2.\* <br>
   FROM Table1 t1, Table2 t2 <br>
   WHERE t1.ID = t2.ID;

- Explicit Syntax
  - SELECT t1.*, t2.\* <br>
   FROM t1 <br>
   INNER JOIN t2 ON t1.ID=t2.ID;

<img src=images/Inner_Join_Table.PNG width=400/img>

***

###  ❖ OUTER JOINS

> **Three Types of Outer Join** <br>

- **Left Outer Join** (*Same as 'Left Join'*)
- **Right Outer Join** (*Same as 'Right Join'*)
- **Full Outer Join** (*MySQL does not support full outer join syntax*) <br>



#### ◆ **LEFT OUTER JOIN**

- Left Join returns all rows from left table with matching rows from 
right table. 
- If no columns matching in right table, returns NULL
values.

<img src=images/Left_Join.PNG width=400/img>

##### **Syntax**

- SELECT t1.ID, t1.Value, <br>
         t2.ID, t2.Value <br>
  FROM t1 <br>
  LEFT JOIN t2 ON t1.ID = t2.ID;

<img src=images/Left_Join_Table.PNG width=400/img>



#### ◆ <**RIGHT OUTER JOIN**

- Returns rows from the right table with matching rows from left
- If no columns matching in left table, returns NULL values

<img src=images/Right_Join.PNG width=400/img>

##### **Syntax**

- SELECT t1. ID, t1.Value <br>
       t2.ID, t2.Value <br>
  FROM t1 <br>
  RIGHT JOIN t2 ON t1.ID = t2.ID;

<img src=images/Right_Join_Table.PNG width=400/img>

***

#### ◆ FULL OUTER JOIN

- Combines left outer join and right outer join
- Returns rows from either table when conditions are met
- Returns a null value when no match
- MySQL does not support syntax <br>
  > **Simulate FULL OUTER JOIN using LEFT** <br> 
  > **and RIGHT join with UNION**




















