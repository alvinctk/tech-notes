
## Nested Queries

Nesting is necessary in the `WHERE` clause because the interpreter is unable to
look outside to figure out any aggregration function. 

Example, 

```sql
SELECT
    first_name,
    last_name
FROM 
    executions
WHERE
    LENGTH(last_statement) = (SELECT MAX(LENGTH(last_statement) FROM executions)
```

## MapReduce


> MapReduce is a famous programming paradigm which views computations as
> occuring in a "map" and "reduce" step. 

According to the [Simple MapReduce explanation](https://stackoverflow.com/questions/28982/simple-explanation-of-mapreduce),

> **Map** is a function that transforms each element in the data. 

```python
A = [1, 2, 3]
A = map(lambda x: x * 2, A)
print(A)
```
```text
[2, 4, 6]
```

> **Reduce** is a function which "collects" items in the data and perform some
> computation on all of them. Thus reducing them into a single item. 

```python
from functools import reduce
total = reduce(lambda x, y: x + y, range(1, 11))
>>> total
```
55





## `WHERE` and `HAVING BY`

`HAVING` block illustrates the filtering of result based on grouping and
aggregration. 

`WHERE` block illustrates the filtering of result **before** grouping and
aggregration. 


## SQL Joins 

![SQL Joins](./sql_joins.jpg)

