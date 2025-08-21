---
  title: Core vs Shared vs Children
  description: Practical distinctions and usage guidelines for core, shared, and children code in Angular projects.
---


## Core vs Shared vs Children

### Core
Code specific to the application and cross-cutting concerns:
- Imported only once (usually in `main.ts`)
- Services are typically `{providedIn: 'root'}` (singleton)
- Examples: interceptors, guards, base classes, global services

### Shared
Reusable code across different features/components:
- Used in multiple places throughout the app
- Examples: UI components, pipes, directives, layouts, modals
- See: [Component, page & layout](https://github.com/o-pinion/angular/wiki/component-page-layout)

### Children
Code only used within a specific feature/folder, not shared elsewhere:
- Feature-specific components, layouts, or services
- Not imported outside their parent folder


```text
pages/
└─ auth/
  ├─ login/
  │   └── login.page.ts
  ├─ signup/
  │   └── signup.page.ts
  └─ layout/
    └── auth.layout.ts
```
