---
title: Endpoint
description: Conventions for naming API endpoints in this project.
---

## Naming Conventions

- Use only `lowercase` letters
- Replace spaces with hyphens (kebab-case): `company-names`
- No file extensions in URLs


## Plural Resource Names

- Always use plural nouns for collections: `/companies`, `/employees`

### Examples

```http
GET /companies
// List all companies
```
```http
GET /companies/34
// Get details of company 34
```
```http
POST /companies
// Create a new company (returns created resource)
```
```http
DELETE /companies/34
// Delete company 34
```


### Nested Resources

```http
GET /companies/3/employees
// List all employees in company 3
```
```http
GET /companies/3/employees/45
// Get details of employee 45 in company 3
```
```http
DELETE /companies/3/employees/45
// Delete employee 45 in company 3
```
