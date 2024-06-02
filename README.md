
# Table of Contents

**Notes on Inner Join**
> - [Inner Join](#-inner-join)

**Notes on Outer Join Types**
> - [Outer Join](#-outer-joins)
>   - [Left Outer Join](#-left-outer-join)
>   - [Right Outer Join](#-right-outer-join) 
>   - [Full Outer Join](#-full-outer-join)
***

#### ◆ INNER JOIN

- Returns rows when there is at least one match in both tables
- Avoid ambiguity by qualifying each column with table name
- Joins tables based on relationships
- Operators: '**=**' , '**>**', '**<**', '**<=**', '**>=**'

</br>
</br>
<img src=images/Inner_Join.PNG width=400/img>
</br>
</br>

**➤ Syntax** 

</br>

- Implicit Syntax
```
   SELECT t1.*, t2.\*
   FROM Table1 t1, Table2 t2
   WHERE t1.ID = t2.ID;
```
- Explicit Syntax
```
   SELECT t1.*, t2.\*
   FROM t1
   INNER JOIN t2 ON t1.ID=t2.ID;
```
</br>

**➤ Sample Output**

</br>
</br>
</br>
<img src=images/Inner_Join_Table.PNG width=400/img>
</br>
</br>

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

**➤ Syntax**
```
  SELECT t1.ID, t1.Value,
         t2.ID, t2.Value
  FROM t1
  LEFT JOIN t2 ON t1.ID = t2.ID;
```
<img src=images/Left_Join_Table.PNG width=400/img>



#### ◆ **RIGHT OUTER JOIN**

- Returns rows from the right table with matching rows from left
- If no columns matching in left table, returns NULL values

<img src=images/Right_Join.PNG width=400/img>

**➤ Syntax**
```
  SELECT t1. ID, t1.Value
       t2.ID, t2.Value
  FROM t1
  RIGHT JOIN t2 ON t1.ID = t2.ID;
```
<img src=images/Right_Join_Table.PNG width=400/img>

#### ◆ FULL OUTER JOIN

- Combines left outer join and right outer join
- Returns rows from either table when conditions are met
- Returns a null value when no match
- MySQL does not support syntax <br>

  > **Simulate FULL OUTER JOIN using LEFT** <br> 
  > **and RIGHT join with UNION**

<img src=images/Full_Outer_Join.PNG width=400/img>

**➤ Syntax**
```
   SELECT t1.ID, t1.Value,
          t2.ID, t2.Value
   FROM t1
   LEFT JOIN t2 ON t1.ID = t2.ID
   UNION
   SELECT t1.ID, t1.Value,
          t2.ID, t2.Value
   FROM t1
   RIGHT JOIN t2 ON t1.ID = t2.ID;
```
<img src=images/Full_Outer_Join_Table.PNG width=400/img>













