# Querying a Database with SQL

This guide reviews the foundational SQL query structure and introduces the `ORDER BY` keyword to organize query results. You’ll also explore the **Chinook** sample database, which simulates data used by a digital media company.

---

## Basic SQL Query Structure

A basic SQL query includes two essential keywords:

### `SELECT`
Specifies which **columns** to return from a table.

### `FROM`
Specifies which **table** to query the data from.

### Example:
sql
SELECT employee_id, device_id
FROM employees;

# SQL Filtering with `WHERE`, `LIKE`, and Wildcards

In this guide, you’ll expand your SQL filtering skills using the `WHERE` clause, the `LIKE` operator, and wildcards like `%` and `_`. These tools help refine queries, especially when dealing with large datasets such as security logs.

---

## Why Filtering Matters

As a security analyst, you’ll frequently work with large, complex logs. Filters help you:

- Find login attempts by a specific user.
- Isolate activity during a known breach.
- Identify devices running specific software versions.

---

## Basic Filtering with `WHERE`

The `WHERE` clause defines conditions that filter which records are returned.

### Example:
``sql
SELECT firstname, lastname, title, email
FROM employees
WHERE title = 'IT Staff';
 This query returns only employees whose title is exactly 'IT Staff'.

 Notes:
Use = to match exact values.

Place the semicolon ; after the filter condition.

 Pattern Filtering with Wildcards
 Wildcards
Wildcard	Description	Example Pattern	Matches
%	Matches any number of characters	'a%'	apple, art, a123
_	Matches exactly one character	'a_'	an, a7, as

You can place these wildcards:

At the start ('%x')

At the end ('x%')

On both sides ('%x%')

 Example Patterns
Pattern	Matches
'a%'	apple123, art, a
'a_'	as, an, a7
'a__'	ant, add, a1c
'%a'	pizza, Z6ra, a
'_a'	ma, 1a, Ha
'%a%'	Again, back, a
'_a_'	Car, ban, ea7

 Filtering with LIKE
The LIKE operator is used with WHERE to filter records by pattern rather than exact value.

 Example – Match Titles:
sql
Copy
Edit
SELECT lastname, firstname, title, email
FROM employees
WHERE title LIKE 'IT%';
 Returns all titles starting with 'IT' (e.g., "IT Staff", "IT Manager").

 Example – Match States:
sql
Copy
Edit
SELECT firstname, lastname, state, country
FROM customers
WHERE state LIKE 'N_';
 Returns results where the state starts with 'N' and is followed by one character, such as: NY, NV, NS, or NT.

 Key Takeaways
Use WHERE to apply filters to your query.

Use LIKE when filtering patterns in string data.

Wildcards:

% matches any number of characters.

_ matches one character only.

Combine these tools to refine your results and extract only what you need.

With these filtering techniques, you’ll be able to handle more complex data queries and better analyze security-related information in databases.



