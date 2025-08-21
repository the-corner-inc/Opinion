---
  title: CSS Naming Convention
  description: Opinionated guidelines for naming CSS classes and IDs.
---


_**Note:** This convention does **not** follow [BEM](https://getbem.com/naming/)—it is lighter and more pragmatic for this project._


## Element
Describe what the object is.

```html
<div class="card"></div>
<div class="toDo"></div>
```


## Type
Clarifies the type or role of the element.
_Examples: `container`, `header`, `content`, `footer`, `list`, `item`, `title`, `description`_

```html
<div class="toDo-container">
  <ul class="toDo-list">
    <li class="toDo-item">
      <h4 class="toDo-title"></h4>
      <p class="toDo-description"></p>
    </li>
  </ul>
</div>
```


## Action
Describes the action or intent of the element.

```html
<div class="button-container">
  <button class="button-delete"></button>
  <button class="button-save"></button>
</div>
```


## Modifier
Flags that change appearance, behavior, or state.
_Examples: `active`, `disabled`, `hidden`, ..._

```html
<div class="button-container">
  <button class="button-delete hidden"></button>
  <button class="button-save disable"></button>
</div>
```


## JavaScript Interactions

### IDs
- Use IDs **only** if they are manipulated by JavaScript (e.g., event listeners, DOM removal).
- **Never** apply CSS to IDs.

### Classes
- If a class is toggled/used by JavaScript, use **camelCase** for the class name.

```html
<div class="card-container" [class.haveBackFace]="true"></div>
```

---

## Best Practices
- Prefer descriptive, readable class names.
- Avoid deep selector nesting.
- Use modifiers for state, not for structure.
- Keep naming consistent across the codebase.
