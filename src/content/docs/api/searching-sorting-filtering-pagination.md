---
title: Searching, Sorting, Filtering, and Pagination
description: Project conventions for searching, sorting, filtering, and paginating API results.
---


All of these actions are handled via query parameters on collection endpoints (e.g., `GET /companies`).
Never create new endpoints for these operations—always use query params.




## Sorting
- Sort results by one or more fields using the `sort` query parameter. 
- Multiple fields can be separated by commas:

```http
GET /companies?sort=rank
GET /companies?sort=rank.asc
GET /companies?sort=rank.desc
GET /companies?sort=rank.desc,name.asc
```

| Operator | Meaning    |
| -------- | ---------- |
| asc      | Ascending  |
| desc     | Descending |



## Filtering
- Filter results by passing field-value pairs as query parameters. 
- Combine multiple filters for AND logic:

```http
GET /companies?category=banking&location=switzerland
```

### Filter Operators
Use operator prefixes for advanced filtering:

```http
GET /companies?category=ne:banking
GET /companies?rank=gt:10
```

| Operator | Meaning                  |
| -------- | ------------------------ |
| (none)   | Equal to                 |
| ne       | Not equal to             |
| gt       | Greater than             |
| ge       | Greater than or equal to |
| lt       | Less than                |
| le       | Less than or equal to    |



## Searching
- Search by keyword(s) using the `search` parameter. 
- By default, search applies to key text fields (e.g., name, title, description):

```http
GET /companies?search=foo
```

To target a specific field, use a field-specific search parameter if supported (e.g., `name_like`):

```http
GET /companies?name_like=foo
```



## Pagination

Paginate results using `page` and `limit` (or `pageSize`) parameters:

```http
GET /companies?page=23
GET /companies?limit=20
GET /companies?page=2&pageSize=50
```

### Infinite Scroll (Cursor-Based)

Use a cursor for efficient pagination:

```http
GET /companies?limit=20&cursor=12345
```

Always return pagination metadata (e.g., totalItems, pageIndex, totalPages) in the response for client navigation.
