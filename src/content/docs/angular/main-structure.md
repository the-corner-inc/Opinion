---
  title: Main Structure
  description: Opinionated guidelines for structuring the main.ts file in Angular applications.
---

# main.ts Structure
How to structure your `main.ts` for clarity, maintainability, and best practices.

## Best Practices

- Place `enableProdMode()` behind the environment check.
- Use `provideAppInitializer` for async app setup before bootstrapping.
- Use `importProvidersFrom` for module imports.
- Register HTTP interceptors and global providers in the `providers` array.
- Keep `main.ts` minimal—move logic to services or initializers.

```typescript
if (environment.production) {
  enableProdMode();
}

export function initApp(fooService: FooService) {
  return async () => {
    await firstValueFrom(
      fooService.initialized$.pipe(
        filter(Boolean),
        take(1),
      ),
    );
  };
}

bootstrapApplication(AppComponent, {
  providers: [
    { provide: VARIABLE, useValue: 'John Doe' },

    { provide: DateAdapter, useClass: FooDateAdapter },

    provideAnimationsAsync(),

    provideAppInitializer(async () => {
      const fooService = inject(FooService);
      await initApp(fooService)();
    }),

    importProvidersFrom(FooModule.forRoot()),

    provideHttpClient(withInterceptors([fooInterceptorFn])),
  ],
});
```
