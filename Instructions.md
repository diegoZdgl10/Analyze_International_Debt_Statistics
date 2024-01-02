# Project Instructions

## Write SQL queries to answer the following:

- What is the number of distinct countries present in the database? The output should be single column aliased with the following name: `total_distinct_countries`.
- What are the distinct debt indicators? the output column should be aliased as `distinct_debt_indicators` and the outputs should be ordered by it.
- What is the total amount of debt owed by all the countries present in the table, in millions? The output should be single column aliased with the following name: `total_debt`.
- What country has the highest amount of debt?
- What is the average amount of debt across different debt indicators?
- What is the highest amount of principal repayments in the "DT.AMT.DLXF.CD" category? 

Six SQL cells have been created for you in the Workspace. To access the database, you will need to select data using the syntax `FROM international_debt`. While accessing the rows of the database you should follow this format: `international_debt.COLUMN_NAME`.

**Note**: Please also ensure that you do not change the names of the DataFrames that the three query results will be saved as - creating new cells in the Workspace will rename the DataFrame. Make sure that your final solutions use the names provided: `num_distinct_countries`, `distinct_debt_indicators`, `total_debt`, `highest_debt_country`, `avg_debt_per_indicator`, and `highest_principal_repayment`.

<br>

## RESOURCES

##### Check resources that can help you solve the problem.

### LESSONS
#### [`SELECT`ing columns exercise from Introduction to SQL](https://campus.datacamp.com/courses/introduction-to-sql/selecting-columns?ex=8)
#### [`LIMIT` exercise from Introduction to SQL](https://campus.datacamp.com/courses/introduction-to-sql/selecting-columns?ex=8)
#### [Exercise on `DISTINCT` from Introduction to SQL](https://campus.datacamp.com/courses/introduction-to-sql/selecting-columns?ex=9)
#### [Aliasing exercise from Introduction to SQL](https://campus.datacamp.com/courses/introduction-to-sql/aggregate-functions?ex=5)
#### [Exercise on `ORDER BY` from Introduction to SQL](https://campus.datacamp.com/courses/introduction-to-sql/sorting-and-grouping?ex=2)
#### [Exercise on _aggregate functions_ from Introduction to SQL](https://campus.datacamp.com/courses/introduction-to-sql/aggregate-functions?ex=2)
#### [`GROUP BY` exercise from Introduction to SQL](https://campus.datacamp.com/courses/introduction-to-sql/sorting-and-grouping?ex=7)
#### [`WHERE` exercise from Introduction to SQL](https://campus.datacamp.com/courses/introduction-to-sql/filtering-rows?ex=2)

### CHEATSHEETS
#### [`COUNT` and `DISTINCT` exercise from Introduction to SQL](https://campus.datacamp.com/courses/introduction-to-sql/selecting-columns?ex=11)

### TUTORIALS
#### [Tutorial on writing subqueries in PostgreSQL](http://www.postgresqltutorial.com/postgresql-subquery/)

<br>

## GUIDES

### How to approach the project
1. Finding the number of distinct countries
2. Finding out the distinct debt indicators
3. Totaling the amount of debt owed by the countries
4. Country with the highest debt
5. Average amount of debt across indicators
6. The highest amount of principal repayments

### 1 Finding the number of distinct countries
- Use the `DISTINCT` clause and the `COUNT()` function in pair on the `country_name` column.
- Alias the resulting column as `total_distinct_countries`.

### 2 Finding out the distinct debt indicators
- Use the `DISTINCT` clause on the `indicator_code` column, aliasing the resultant column as `distinct_debt_indicators`.
- Order the results by `distinct_debt_indicators`.

### 3 Totaling the amount of debt owed by the countries
- Use the built-in `SUM` function on the `debt` column, then divide it by 1,000,000 and round the result to 2 decimal places so that the output is fathomable.
- Alias the resulting column as `total_debt`.

### 4 Country with the highest debt
- Select the `country_name` and `debt` columns, then apply the `SUM` function on the `debt` column.
- Alias the column resulted from the summation as `total_debt`.
- `GROUP` the results `BY` `country_name` and `ORDER` them `BY` the new alias `total_debt` in a descending manner.
- `LIMIT` the number of rows to be one.

### 5 Average amount of debt across indicators
- Select `indicator_code` aliased as `debt_indicator`, then select `indicator_name` and `debt`.
- Apply an aggregate function on the `debt` column to average out its values and alias it as `average_debt`.
- Group the results by the newly created `debt_indicator` and already present `indicator_name` columns.
- Sort the output with respect to the `average_debt` column in a descending manner and limit the results to ten.

### 6 The highest amount of principal repayments
- Select the `country_name` and `indicator_name` columns.
- Add a `WHERE` clause to filter out the maximum `debt` in the "DT.AMT.DLXF.CD" category. 