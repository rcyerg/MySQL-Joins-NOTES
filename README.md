## MySQL-Joins-NOTES
***

### JOINS

#### Inner Join

- Returns rows when there is at least one match in both tables
- Avoid ambiguity by qualifying each column with table name
- Join tables based on relationships
- Operators: = > < <= >=

##### Syntax 

- Implicit Syntax
  - SELECT t1.*, t2.\*\
   FROM Table1 t1, Table2 t2\
   WHERE t1.ID = t2.ID;

- Explicit Syntax
  - SELECT t1.*, t2.\*\
   FROM Table1 t1\
   INNER JOIN Table2 t2 ON t1.ID=t2.ID;


#### OUTER JOIN


**Three Types of Outer Join**

- Left Outer Join (*Same as 'Left Join'*)
- Right Outer Join (*Same as 'Right Join'*)
- Full Outer Join (*MySQL does not support full outer join syntax*)





































