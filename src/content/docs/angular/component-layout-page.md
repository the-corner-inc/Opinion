---
  title: Components vs Layouts vs Pages
  description: Why not everything should be a component, and how to organize UI code for scalability.
---


## Why Not Everything Is a Component?

_See visual example: [Component, page & layout](https://github.com/o-pinion/angular/wiki/component-page-layout)_

In large projects, a flat `components` folder quickly becomes unmanageable. To reduce complexity and improve maintainability, split UI code into these categories:

### Components
Reusable UI elements that are not pages or layouts.
- **Examples:** `Card`, `Sidebar`, `Table`
- **Naming:**
  - File: `card.component.ts`
  - Class: `CardComponent`

### Pages
Route destinations, mapped to URLs.
- **Examples:** `Home`, `Login`, `Blogs`
- **Naming:**
  - File: `home.page.ts`
  - Class: `HomePage`

### Layouts
Define structure/positioning of UI areas.
- **Examples:** Main layout (sidenav, content, footer), Auth layout, Article layout
- **Naming:**
  - File: `main.layout.ts`
  - Class: `MainLayout`

### Other Logical Folders
Move logical elements (e.g., `modals`, `buttons`) into their own folder if there are more than three components. Avoid creating folders for just a few files.
- **Naming:**
  - File: `[name].[element].ts`
  - Class: `[Name][Element]`

_Tip: Avoid dumping everything in `components`—categorize for clarity and maintainability._
