---
  title: Service Structure
  description: Opinionated guidelines for structuring Angular services.
---



## Where to Provide Services

### Core services
Imported only once and used across the entire application.
- Provided in `root` (singleton)
- Imported in `main.ts` only
- Examples: `AppThemeService`, `SessionService`, `DarkModeService`

```typescript
@Injectable({ providedIn: 'root' })
export class SessionService { /* ... */ }
```

**Folder structure:**
```typescript
src/app/core/services/
  ├── [name].service.ts
  ├── session.service.ts
  └── dal.service.ts
```

### Shared services
Used in multiple places, provided in feature/shared modules or components.
- Not provided in root
- Examples: `UserService`, `LabelService`, `LoaderService`

```typescript
@Injectable()
export class LoaderService { /* ... */ }
```

**Folder structure:**
```typescript
src/app/shared/services/
  └── loader.service.ts
```

### Folder structure
```typescript
src/app/shared/services/
  └── loader.service.ts  // <-- Here
```


### Local services
Provided directly in a single component or feature module.
- Used for encapsulated, page-specific logic

```typescript
@Injectable()
export class PageService { /* ... */ }
```

**Folder structure:**
```typescript
src/app/pages/[page]/
  ├── [page].component.html
  ├── [page].component.ts
  ├── [page].module.ts
  └── [page].service.ts
```


### How to Provide

**In a module:**
```typescript
@NgModule({
  providers: [PageService],
})
```

**In a standalone component:**
```typescript
@Component({
  providers: [PageService],
})
```


## Naming Conventions & Method Patterns

Service names and methods should be standardized for reusability and clarity. See [API logic structure](https://github.com/o-pinion/api/wiki).

**Method naming:**

- Use `$item`/`$items` for signals/observables
- Use `getItem`, `getItems`, `addItem`, `addItems`, `putItem`, `deleteItem`, `deleteItems` for CRUD

```typescript
@Injectable()
export class MyService {
  $items = signal<any[]>([]);
  $item = signal<any>();

  getItem() {}
  getItems() {}
  addItem() {}
  addItems() {}
  putItem() {}
  deleteItem() {}
  deleteItems() {}
}
```
