# Optimize SQL Query

> Each query tells **what** we want, but does not say **how**.

The **how** determines the efficiency of SQL queries. 


## Avoid using functions in `WHERE` clause 

Functions can be used within `SELECT` and in the `WHERE` clause. 

Inefficient queries arises from usage of functions in `WHERE` clause. 

```sql 
SELECT
    name 
FROM 
    table
WHERE
    EXTRACT(year FROM table) = 2021
```

Suppose there is a index on `order_date` column. The query needs to perform
full-table scan because we use `EXTRACT` function on the column `order_date`.

Instead of full-table scan, query using the index column for faster
performance. 

```sql
SELECT
    name
FROM
    table
WHERE
    order_date > '2021-01-01'
```


## Avoid using wildcard characters at the start of the pattern

Having wildcard characters at the beginning means the SQL query needs to do a
full-table scan by looking at each row regardless if column name is indexed. 

Further reads on  [Sargability: Why %string% is slow](https://www.brentozar.com/archive/2010/06/sargable-why-string-is-slow/).

## Avoid sub queries. Use temp table. 

Temp tables allows you to 
- reuse query multiple times which in turn reduces table scans.

- using temp table allow us the flexibility of using index or which keys to
  optimize joins. 


## Avoid using `SELECT *`. 

Select the columns that you need.


## Avoid using `DISTINCT` and `ORDER BY` unless you need to 

Using `DISTINCT` and `ORDER BY` are costly opertion because query output needs
to be sorted and checked for duplicates. These commands are always processed
towards the end of query before `LIMIT`. 

Use `GROUP BY` instead of `DISTINCT` to get distinct values. 


## Create indexes to speed up SQL query

In general, index is a `B-Tree`. There are two types of indexes: clustered and
non-clustered. 

> **Clustered** index creates a physical order of rows in the table. There can
only be one clustered index in the table. A primary key is also a clustered
index. 

> **Nonclustered** index is a `binary tree` but it does not create a physical
order of rows in the table. Hence, the leaf nodes of nonclustered index contain
Primary Key (PK) if PK exists or row index. 

Indexes are used to increase the speed of search because the time complexity of
using indexes to search is O(log N).

Read article [use the index by Luke](https://use-the-index-luke.com) to know
more about SQL index. 

```sql
CREATE INDEX INDEX_NAME ON TABLE_NAME(COLUMN)
```


## Understand SQL Query Cost

Use `EXPLAIN` or `EXPLAIN QUERY PLAN` to find out the query cost

```sql
EXPLAN QUERY PLAN SELECT * FROM table
```
> Use `EXPLAIN` as a reference than as an absolute measure. 




