# Backend and API Interview Prep

## Baseline Topics

- REST API design
- HTTP methods
- HTTP status codes
- Request validation
- Authentication basics
- Error handling
- Logging

## Starter Questions

1. What makes an API RESTful?
2. When should an API return `200`, `201`, `400`, `401`, `403`, `404`, or `500`?
3. What is the difference between authentication and authorization?
4. How would you debug a slow API endpoint?

## Week 01 Notes - Status Codes and Validation

Common status code decisions:

- `200 OK`: request succeeds, including list/search endpoints with an empty result such as `[]`.
- `201 Created`: a new resource is created, such as `POST /api/books`.
- `204 No Content`: request succeeds and no response body is needed, such as a successful delete.
- `400 Bad Request`: invalid query parameter, path parameter, or request body.
- `401 Unauthorized`: the user is not authenticated or the token is missing, invalid, or expired.
- `403 Forbidden`: the user is authenticated but does not have permission.
- `404 Not Found`: a specific requested resource does not exist, such as `GET /api/books/123`.
- `500 Internal Server Error`: the backend fails unexpectedly, such as a database connection error.

Backend validation is mandatory even when frontend validation exists. Frontend validation improves UX, but it can be bypassed. The backend must validate query params, path params, and request bodies before using them in business logic or database queries.

## Week 01 Interview Questions

1. Why should `GET /api/books?search=unknown` return `200 OK` with `[]` instead of `404 Not Found`?
2. Why should `GET /api/books?page=abc` return `400 Bad Request`?
3. What is the difference between `401 Unauthorized` and `403 Forbidden`?
4. Why should invalid request data be rejected before querying the database?
5. What should the backend return if the database fails while processing a valid request?
