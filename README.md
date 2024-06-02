
## MySQL-Joins-NOTES


### JOINS
***

#### ◆ INNER JOIN <br>

- Returns rows when there is at least one match in both tables
- Avoid ambiguity by qualifying each column with table name
- Join tables based on relationships
- Operators: = > < <= >=

##### **Syntax** 

- Implicit Syntax
  - SELECT t1.*, t2.\* <br>
   FROM Table1 t1, Table2 t2 <br>
   WHERE t1.ID = t2.ID;

- Explicit Syntax
  - SELECT t1.*, t2.\* <br>
   FROM Table1 t1 <br>
   INNER JOIN Table2 t2 ON t1.ID=t2.ID;

<img src=images/Inner_Join.PNG width=200/img>

#### ◆ OUTER JOIN <br>

> **Three Types of Outer Join** <br>

- Left Outer Join (*Same as 'Left Join'*)
- Right Outer Join (*Same as 'Right Join'*)
- Full Outer Join (*MySQL does not support full outer join syntax*)

Left Join returns all rows from left table with matching rows from 
right table. If no columns matching in right table, returns NULL
values. <br>





































