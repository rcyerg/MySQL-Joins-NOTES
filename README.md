
# Table of Contents

**Notes on Inner Join**
> - [Inner Join](#-inner-join)

**Notes on Outer Join Types**
> - [Outer Join](#-outer-joins)
>   - [Left Outer Join](#-left-outer-join)
>   - [Right Outer Join](#-right-outer-join) 
>   - [Full Outer Join](#-full-outer-join)

**Notes on Cross Join**
> - [Cross Join](#-cross-join)

**Notes on Equi and Non-Equi Joins**
> - [Equi and Non-Equi Joins](#-equi-join-and-non-equi-join)
>   - [Equi Join](#-equi-join)
>   - [Non-Equi Join](#-non-equi-join)

**Notes on Self Join**
> - [Self Join](#-self-join)

***

#### ❖ INNER JOIN

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

- *Implicit Syntax*
```
   SELECT Table1.*, Table2.*
   FROM Table1 Table1, Table2 Table2
   WHERE Table1.ID = Table2.ID;
```
- *Explicit Syntax* (further examples use explicit)
```
   SELECT Table1.*, Table2.*
   FROM Table1
   INNER JOIN Table2 ON Table1.ID=Table2.ID;
```
</br>

**➤ Sample Output**

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
- **Full Outer Join** (*MySQL does not support full outer join syntax*)

</br>
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -  -
</br>

#### ◆ **LEFT OUTER JOIN**

- Left Join returns all rows from left table with matching rows from 
right table. 
- If no columns matching in right table, returns NULL
values.

</br>
</br>
<img src=images/Left_Join.PNG width=400/img>
</br>
</br>

**➤ Syntax**

</br>

```
  SELECT Table1.ID, Table1.Value,
         Table2.ID, Table2.Value
  FROM Table1
  LEFT JOIN Table2 ON Table1.ID = Table2.ID;
```

</br>

**➤ Sample Output**

</br>
</br>
<img src=images/Left_Join_Table.PNG width=400/img>
</br>
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
</br>

#### ◆ **RIGHT OUTER JOIN**

- Returns rows from the right table with matching rows from left
- If no columns matching in left table, returns NULL values

</br>
</br>
<img src=images/Right_Join.PNG width=400/img>
</br>
</br>

**➤ Syntax**

</br>

```
  SELECT Table1. ID, Table1.Value
       Table2.ID, Table2.Value
  FROM Table1
  RIGHT JOIN Table2 ON Table1.ID = Table2.ID;
```

</br>

**➤ Sample Output**

</br>
</br>
<img src=images/Right_Join_Table.PNG width=400/img>
</br>
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
</br>

#### ◆ FULL OUTER JOIN

- Combines left outer join and right outer join
- Returns rows from either table when conditions are met
- Returns a null value when no match
- MySQL does not support syntax <br>

  > **Simulate FULL OUTER JOIN using LEFT** <br> 
  > **and RIGHT join with UNION**

</br>
</br>
<img src=images/Full_Outer_Join.PNG width=400/img>
</br>
</br>

**➤ Syntax**

</br>

```
   SELECT Table1.ID, Table1.Value,
          Table2.ID, Table2.Value
   FROM Table1
   LEFT JOIN Table2 ON Table1.ID = Table2.ID
   UNION
   SELECT Table1.ID, Table1.Value,
          Table2.ID, Table2.Value
   FROM Table1
   RIGHT JOIN Table2 ON Table1.ID = Table2.ID;
```

</br>

**➤ Sample Output**

</br>
</br>
<img src=images/Full_Outer_Join_Table.PNG width=400/img>
</br>
</br>

***

#### ❖ CROSS JOIN

- A Cartesian join that does not necessitate
  any condition to join
- result set contains records that are multiples of
  the record number of both the tables

</br>
</br>
<img src=images/Cross_Join.PNG width=400/img>
</br>
</br>

**➤ Syntax**

</br>

```
   SELECT Table1.ID, Table1.Value
          Table2.ID, Table2.Value
   FROM Table1
   CROSS JOIN Table2;
```

</br>

**➤ Sample Output**

</br>
</br>
<img src=images/Cross_Join_Table_1.PNG width=200/img>
<img src=images/Cross_Join_Table_2.PNG width=200/img>
<img src=images/Cross_Join_Table_3.PNG width=200/img> 
</br>
</br>

***

### ❖ EQUI JOIN and NON EQUI JOIN

</br>

> **Two types of Equi Joins**

</br>

#### ◆ EQUI JOIN 

- A comparator-based join that uses
  only equality comparisons in the join-predicate

</br>

  **➤ Syntax**

</br>

```
   SELECT Table1.*, Table2.*
   FROM Table1
   INNER JOIN Table2 ON Table1.ID = Table2.ID
```
</br>

#### ◆ NON EQUI JOIN

- A comparator-based join that
  **does not** use equality
  comparisons in the join-predicate

</br>

  **➤ Syntax**

</br>

```
   SELECT Table1.*, Table2.*
   FROM Table1
   INNER JOIN Table2 ON Table1.ID > Table2.ID
```
</br>

> **Can use OUTER JOIN in both the above syntaxes**
> **as well**

</br>

***

### ❖ SELF JOIN

- A join in which a table is joined with itself
- User must alias tables used in self join
- User must qualify each column name used
  in SELECT clauses with a table alias to
  avoid ambiguity

 </br>

  **➤ Syntax**

</br>

```
   SELECT t1.*, t2.*
   FROM Table1 t1
   INNER JOIN Table1 t2 ON t1.ID > t2.ID;
```
</br> 

***Self Join Example***: 

</br>

 **➤ Given Table**

</br>
</br>
<img src=images/Self_Join_Initial_Table.PNG width=400/img>
</br>
</br>

 **➤ Given Query**

</br>

```
   SELECT e1.Name EmployeeName, e2.name AS ManagerName
   FROM Employee e1
   INNER JOIN Employee e2
   ON e1.ManagerID = e2.EmployeeID;
```
</br> 

**➤ Sample Output**

</br>
</br>
<img src=images/Self_Join_Result_Table_1.PNG width=400/img>
</br>
</br>

