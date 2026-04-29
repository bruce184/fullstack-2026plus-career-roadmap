# System Design Interview Prep

## Baseline Topics

- Requirements
- API boundaries
- Data modeling
- Caching basics
- File storage basics
- Background jobs
- Failure handling

## Starter Questions

1. How would you start designing a small full-stack application?
2. How do frontend, backend, and database responsibilities differ?
3. When might caching help?
4. How would you explain trade-offs in a design?

## Week 01 Notes - Full-stack Request Flow

For `GET /api/books`, the request flow is:

1. User clicks "View All Books".
2. Frontend shows a loading state and sends `GET /api/books`.
3. Backend receives the request.
4. Backend checks authentication and authorization if required.
5. Backend validates query parameters such as `page`, `limit`, and `search`.
6. Backend queries the database only after validation succeeds.
7. Database returns matching records, an empty result, or an error.
8. Backend returns a safe HTTP status code and JSON response.
9. Frontend renders success, empty, validation error, auth, permission, network, or page-level error state.

Layer responsibilities:

- Frontend: user interaction, API calls, and UI states.
- Backend: validation, auth/authz, business logic, database access, and safe responses.
- Database: data storage, query execution, and query results.

Interview answer:

```text
When the user clicks "View All Books", the frontend handles the user action and shows a loading state. It sends a GET request to /api/books. The backend receives the request, checks authentication and authorization if required, validates query parameters such as page, limit, or search, then queries the database. The database returns the matching records to the backend. The backend sends back an HTTP status code and a JSON response. Finally, the frontend updates the UI by showing a success state with data, an empty state if the array is empty, or an error/auth/permission state if the request fails.
```
