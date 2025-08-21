---
title: HTTP Methods
description: Project conventions for HTTP methods in API endpoints.
---

## GET
- Retrieve data from a resource. 
- **Must not** produce side effects.

```http
GET /companies/3/employees
// Returns all employees from company 3
```

## POST
- **Create** a new resource.
- **Not idempotent**: multiple identical requests create multiple resources.

```http
POST /companies/3/employees
// Creates a new employee in company 3
```

## PUT
- **Replace** a resource, or create it if it does not exist.
- **Idempotent**: repeated requests have the same effect.

```http
PUT /companies/3/employees/4
// Replaces employee 4 in company 3, or creates if not present
```

## DELETE
- **Remove** a resource.
- Idempotent: repeated requests have the same effect.

```http
DELETE /companies/3/employees/4
// Deletes employee 4 from company 3
```

## PATCH
- **Partially update** a resource (only the provided fields).
- Idempotent: repeated requests with the same data have the same effect.

```http
PATCH /companies/3/employees/4
// Updates only specified fields of employee 4 in company 3
```
