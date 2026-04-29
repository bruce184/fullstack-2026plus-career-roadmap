# Frontend Interview Prep

## Baseline Topics

- Browser rendering
- HTTP request and response flow
- Client-server architecture
- HTML, CSS, and JavaScript responsibilities
- Basic accessibility
- Basic performance

## Starter Questions

1. What happens when a user enters a URL in the browser?
2. What is the difference between HTML, CSS, and JavaScript?
3. What can make a web page feel slow?
4. How do browser DevTools help debug frontend issues?

## Week 01 Notes - API UI States

When the frontend calls an API, it should handle the main user-facing states:

- Loading: the request is in progress.
- Success: the API returns data and the UI can render it.
- Empty: the API succeeds but returns no records, such as `200 OK` with `[]`.
- Validation error: the API returns `400 Bad Request` for invalid query, path, or body data.
- Auth state: the API returns `401 Unauthorized`, so the user needs to log in or refresh authentication.
- Permission error: the API returns `403 Forbidden`, so the authenticated user does not have permission.
- Page-level error: the network fails or the server returns `500 Internal Server Error`.

Field-specific or control-specific validation errors should appear near the input/control that the user can fix. General server or network errors should appear as a page-level or form-level message with a safe retry action.

## Week 01 Interview Questions

1. How should the frontend handle `200 OK` with an empty array?
2. What UI state should be shown while an API request is still running?
3. What is the frontend difference between `401 Unauthorized` and `403 Forbidden`?
4. Where should the UI display a validation error for `page=abc`?
5. Why should detailed database errors not be shown to users?
