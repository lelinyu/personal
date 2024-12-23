# Lecture 25 SQL II

1. Questions
2. Review
    1. Row represents each data point
    2. Column corresponds to a features of each data point
3. Querying a database
    1. SELECT Query
4. Numerical and String Expressions
    1. Expressions
        1. Don’t necessarily have to SELECT information directly from columns in SQL
        2. Can use || to concatenate strings together
        3. Create numeric expressions that do operations on our data
            1. Transforming values: ABS(), ROUND(), NOT, -
            2. <> is equivalent to !=
        4. Selecting substrings: SUBSTR()
            1. SUBSTR(city, 1, 3)
                1. [1-3] Inclusive
    2. Aggregate Functions
        1. Allow us to compare across all the rows in a table
        2. MAX()
    3. Mixing Aggregation and Single Values
        1. If we include a non-aggregated column, SQL will still fill that column with a value
        2. SELECT city, MIN(pop_2020) FROM pop_area_2010;
5. Grouping
    1. Creating Tables from Tables
        1. Grouping
            1. We can divide our table into groups, then aggregate within those groups, instead of aggregating across entire table
            2. Using sum or average, it can just take an arbitrary song name
        2. Grouping by expressions
    2. Final Query Structure and Order of Operations

```sql
SELECT
FROM
WHERE
GROUP BY
HAVING
ORDER BY
LIMIT
```

1. Database Connections
    1.