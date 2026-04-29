# Database Interview Prep

## Baseline Topics

- Tables and relationships
- Primary keys and foreign keys
- Indexes
- Transactions
- Query planning
- Slow query debugging

## Starter Questions

1. What is an index and when can it help?
2. What is a transaction?
3. What are common causes of slow SQL queries?
4. How would you model a one-to-many relationship?

## Week 01 Notes - Database Role in Request Flow

The database is responsible for storing data, executing queries sent by the backend, and returning query results to the backend. It should not communicate directly with the frontend.

For list endpoints, the backend commonly uses pagination values before querying:

- `page`: current page number.
- `limit`: number of records per page.
- `offset`: `(page - 1) * limit`.
- `total`: total number of matching records.
- `totalPages`: `Math.ceil(total / limit)`, or `0` when `total = 0`.

Example:

```sql
SELECT *
FROM books
ORDER BY id
LIMIT 10 OFFSET 10;
```

This query returns page 2 when `limit = 10`.

## Week 01 Interview Questions

1. Why should the frontend not query the database directly?
2. What is the database responsible for in a full-stack request flow?
3. How are `page`, `limit`, and `offset` related?
4. If `total = 57` and `limit = 10`, how many pages are there?
5. What should `totalPages` be when `total = 0`?
