## Pattern Matching 
Pattern matching uses keyword `LIKE` and (`%` and `_`) wildcard symbols.

`%` wildcard matches zero or more characters of any type. The wildcard can be
used before, after, or both (before and after) the pattern. 

`_` wildcard matches any character for one character position. 

- First name beginning with letter A
```sql
SELECT
    *
FROM
    students
WHERE
    first_name LIKE "A%"
```

- Omitting patterns using `NOT` keyword
```sql
SELECT
    *
FROM
    students
WHERE
    first_name NOT LIKE "%A%"
```

- Specific location  using `_` wildcard - third character is `A`
```sql
SELECT
    *
FROM
    students
WHERE
    first_name LIKE "__A%"

```
- n or more letters - 4 or more letters
```sql
SELECT
    *
FROM
    students
WHERE
    first_name LIKE "____%"

```

- exactly n letters - exactly 4 letters
```sql
SELECT
    *
FROM
    students
WHERE
    first_name LIKE "____"

```





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

## View

A view is a logical snapshot based on a table or another view. It is used 
- Restricting access to data
- Making complex queries simple
- Ensuring data independency
- Providing different views of same data





## `WHERE` and `HAVING BY`

`HAVING` block illustrates the filtering of result based on grouping and
aggregration. 

`WHERE` block illustrates the filtering of result **before** grouping and
aggregration. 


## SQL Joins 

![SQL Joins](./sql_joins.jpg)


## Common Table Expressions 
The only way to declare variables in SQL


## Window Function

```sql
-- Aggregrations / rankings on a subset of rows relative to the current row being transformed by SELECT

function (...) OVER (
    PARTITION BY ...
    ORDER BY ...
    ROWS BETWEEN ... AND ...
)
```

### Getting a running total 
Given table `Accounts` with columns `event_date`, and `amount`. Find the running total
at each `event_date`.

```sql
SELECT 
    event_date,
    SUM(amount) over (ORDER BY event_date ASC) AS running_total
FROM
    Accounts
ORDER BY
    event_date ASC
```

### Populate total count in each row
```sql 
SELECT 
    whatever_columns,
    COUNT(*) OVER() as total_count 
FROM
    table
```

### Getting the N most recent rows over mutliple goruping
```sql
WITH CTE AS (
    SELECT 
        *,
        ROW_NUMBER() OVER (PARTITION BY user_id 
                           ORDER BY completion_date DESC) AS rn
    FROM
        Table


SELECT * FROM CTE WHERE rn <= n 
)
```

`ROW_NUMBER` is a function. 



