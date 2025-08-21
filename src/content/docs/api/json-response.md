---
title: JSON Response
description: Project conventions for structuring JSON API responses.
---


_Inspired by [Google JSON Style Guide](https://google.github.io/styleguide/jsoncstyleguide.xml)_


Balance ease of use for consumers with stability and predictability for clients.



## Response Structure

### Single Item
```json
{
  "attributes": {
    "id": 123,
    "title": "...",
    "subTitle": "...",
    "description": "...",
    // ...
    "items": [ /* nested items */ ]
  },
  "error": {
    "code": 404,
    "message": "Not found",
    "details": "..."
  }
}
```

### Multiple Items
```json
{
  "items": [ /* array of attributes */ ],
  "error": {
    "code": 400,
    "message": "Bad request",
    "details": "..."
  }
}
```


## Attributes

### Required
- `id` (string or number): Unique identifier for the resource.

### Optional (when relevant)
- `title`, `subTitle`, `description`, `content`
- `items`: Always the last attribute if present (for nested/related data)


## Reserved Property Names & Structure
The following names are reserved for consistency. Use them when relevant, and keep the order consistent:

 

```json
{
  "apiVersion": "1.0",
  "context": "...",
  "id": "...",
  "method": "GET",
  "messages": [],
  "attributes": {
    "id": "...",
    "foreignKeyId": "...",
    "type": "...",
    "title": "...",
    "subTitle": "...",
    "description": "...",
    "content": "...",
    "fields": "...",
    "etag": "...",
    "lang": "en",
    "updated": "2025-08-21T12:00:00Z",
    "deleted": false,
    "currentItemCount": 10,
    "itemsPerPage": 10,
    "startIndex": 0,
    "totalItems": 100,
    "pageIndex": 1,
    "totalPages": 10,
    "pageLinkTemplate": "...",
    "next": {},
    "nextLink": "...",
    "previous": {},
    "previousLink": "...",
    "self": {},
    "selfLink": "...",
    "edit": "...",
    "editLink": "...",
    "translations": [],
    "items": []
  },
  "items": [],
  "error": {
    "code": 400,
    "message": "...",
    "errors": []
  }
}
```
