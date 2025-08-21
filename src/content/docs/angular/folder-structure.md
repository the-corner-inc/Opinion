---
  title: Folder Structure
  description: Opinionated guidelines for organizing files and folders in Angular projects.
---


## Naming Conventions

- Use **kebab-case** for all folders and files.
- Folder names should become increasingly specific **from left to right**.



```text
src/
└─ app/
  └─ pages/
    └─ home/
      ├── home.page.ts
      └─ home-description/
        └── home-description.component.ts
```


## Example Structure

_Note: + indicates that the folder has additional files._


```text
public/
├─ fonts/
├─ i18n/
├─ icons/           # [name]-[direction]-[color].svg
├─ img/
│   └─ components/
│       └─ [page, component, ...]-[name]/
│           ├── bg-desktop.jpg
│           └── bg-mobile.jpg
├─ js/
├─ json/
├─ pdf/
└─ video/

src/
├─ app/
│   ├─ pages/
│   │   ├─ auth/
│   │   │   ├─ login/
│   │   │   ├─ register/
│   │   │   └─ auth-layout/
│   │   └─ [page]/
│   │       ├── [page].page.html
│   │       ├── [page].page.scss
│   │       ├── [page].page.ts
│   │       ├── [page].module.ts
│   │       └─ [page]-[name]/
│   │           ├── [page]-[name].component.html
│   │           ├── [page]-[name].component.scss
│   │           ├── [page]-[name].component.ts
│   │           ├── [page]-[name].module.ts
│   │           └─ [components, modals, ...]/
│   ├─ configs/
│   │   ├── [name].config.ts
│   │   └── global.config.ts
│   ├─ core/
│   │   ├─ animations/
│   │   │   └── global.ts
│   │   ├─ interceptors/
│   │   │   ├── version.interceptor.ts
│   │   │   └── auth.interceptor.ts
│   │   ├─ guards/
│   │   │   ├── auth.guard.ts
│   │   │   └── admin.guard.ts
│   │   ├─ directives/
│   │   │   └── validation.directive.ts
│   │   ├─ services/
│   │   │   ├── dal.service.ts
│   │   │   ├── session.service.ts
│   │   │   └── [another-api].service.ts
│   │   ├─ bases/
│   │   │   └── base-[type].[service|query|component].ts
│   │   └─ models/
│   │       ├── core.enums.ts
│   │       ├── core.d.ts // interfaces
│   │       ├── core.models.ts
│   │       └── core.types.ts
│   └─ shared/
│       ├─ components/
│       │   └── [name]/
│       │       └── [name].component.ts
│       ├─ layouts/
│       │   └── [name]/
│       │       └── [name].layout.ts
│       ├─ modals/
│       │   └── [name]/
│       │       └── [name].modals.ts
│       ├─ pipes/
│       │   └── [name]/
│       │       └── [name].pipe.ts
│       ├─ services/
│       │   └── [name]/
│       │       └── [name].service.ts
│       └─ vendors/
│           ├─ components/
│           │   └── [name].component.ts
│           └─ layouts/
│               └── [name].layout.ts
├─ environments/
│   ├── environment.prod.ts
│   └── environment.ts
└─ styles/
  ├─ base/
  │   ├── _colors.scss
  │   ├── _img.scss
  │   ├── _reset.scss
  │   └── _typography.scss
  ├─ components/
  │   ├── _buttons.scss
  │   └── _gallery.scss
  ├─ themes/
  │   ├── _admin.scss
  │   └── _theme.scss
  ├─ utils/
  │   ├── _functions.scss
  │   ├── _mixins.scss
  │   └── _variables.scss
  ├── _shared.scss
  └── main.scss
```


## Folder Purpose & Best Practices

| Folder       | Description                                |
| ------------ | ------------------------------------------ |
| **public**   | Static assets (fonts, images, icons, etc.) |
| **pages**    | Route destinations (mapped to URLs)        |
| **configs**  | Global config and constants                |
| **core**     | App core logic, cross-cutting concerns     |
| - guards     | Route guards (auth, admin, etc.)           |
| - store      | State management                           |
| - services   | API/database access                        |
| - bases      | Base classes for inheritance               |
| - models     | Enums, interfaces, types, models           |
| **shared**   | Reusable code across the app               |
| - components | UI elements used in multiple places        |
| - directives | Custom directives (e.g., longPress)        |
| - layouts    | Layout containers                          |
| - modals     | Reusable modal dialogs                     |
| - pipes      | Data transformation in templates           |
| - vendors    | Third-party code                           |


## TypeScript Path Aliases
Add these to your [tsconfig.json](https://www.typescriptlang.org/tsconfig/#paths) for easier imports:

```typescript
"baseUrl": "./src",
"paths": {
  "@auth/*": ["app/pages/auth/*"],
  "@pages/*": ["app/pages/*"],
  "@configs/*": ["app/configs/*"],
  "@bases/*": ["app/core/bases/*"],
  "@guards/*": ["app/core/guards/*"],
  "@store/*": ["app/core/store/*"],
  "@models/*": ["app/core/models/*"],
  "@services/*": ["app/core/services/*"],
  "@components/*": ["app/shared/components/*"],
  "@directives/*": ["app/shared/directives/*"],
  "@layouts/*": ["app/shared/layouts/*"],
  "@modals/*": ["app/shared/components/modals/*"],
  "@pipes/*": ["app/shared/pipes/*"],
  "@vendors/*": ["app/shared/vendors/*"],
  "@shared/*": ["app/shared/*"],
  "@app/*": ["app/*"],
}
```


## Thought
This structure is designed for scalability and maintainability. Integrating additional libraries (NgRx, TanStack, etc.) may require adjustments, but the core principles remain the same.

If you have any suggestions that could help others, please feel free to open a [PR](https://github.com/o-pinion/angular/pulls).


## Acknowledgments
- [Mathis Garberg - How to define a highly scalable folder structure for your Angular project](https://itnext.io/choosing-a-highly-scalable-folder-structure-in-angular-d987de65ec7)
- [Radek Busa - “Where Shall I Put That?”— Core vs Shared Module in Angular](https://levelup.gitconnected.com/where-shall-i-put-that-core-vs-shared-module-in-angular-5fdad16fcecc)
