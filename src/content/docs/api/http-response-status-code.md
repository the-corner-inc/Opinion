---
title: HTTP Response Status Codes
description: Project conventions for HTTP response status codes.
---



_Always return the most appropriate HTTP status code for each API response._

## 1xx: Informational
*Rarely used in APIs. Typically not needed in application logic.*

on creating a new instance, using POST method, should always return 201 status code E.g .
## 2xx: Success

### 200 OK
Standard response for successful GET, PUT, or POST requests.

### 201 Created
Returned when a new resource is created (e.g., after POST).

### 204 No Content
Request processed successfully, but no content is returned (e.g., after DELETE).

## 3xx: Redirection

### 304 Not Modified
Resource not changed since last request (client can use cached version).

## 4xx: Client Error

### 400 Bad Request
Malformed request or validation error.

### 401 Unauthorized
Authentication required or failed.

### 403 Forbidden
Authenticated, but not permitted to access the resource.

### 404 Not Found
Resource does not exist.

### 409 Conflict
Request could not be completed due to a conflict (e.g., duplicate data).

### 410 Gone
Resource is permanently removed and will not be available again.

## 5xx: Server Error

### 500 Internal Server Error
Unexpected server error. Avoid exposing internal details.

### 502 Bad Gateway
Server received an invalid response from upstream.

### 503 Service Unavailable
Server is temporarily unavailable (e.g., maintenance or overload).
