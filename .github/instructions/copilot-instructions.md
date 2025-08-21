# Copilot Instructions for AI Coding Agents

## Project Overview

- This is an Astro + Starlight documentation site, opinionated for Angular dev projects.
- Content lives in `src/content/docs/` as `.md` or `.mdx` files. Each file becomes a route.
- Site configuration is in `astro.config.mjs` (sidebar, integrations, site metadata).
- Content schema and collection setup is in `src/content.config.ts`.
- Static assets: `public/` (served as-is), `src/assets/` (for embedding in docs).

## Developer Workflows

- **Install dependencies:** `npm install`
- **Start dev server:** `npm run dev` (serves at `localhost:4321`)
- **Build for production:** `npm run build` (outputs to `./dist/`)
- **Preview build:** `npm run preview`
- **Astro CLI:** `npm run astro ...` (e.g., `astro add`, `astro check`)
- **Content updates:** Edit or add `.md`/`.mdx` in `src/content/docs/`.
- **Sidebar/navigation:** Update `astro.config.mjs` under the `sidebar` key.

## Style

- Use consistent heading levels (e.g., H2 for main sections, H3 for subsections).
- Keep code snippets and examples up-to-date with the latest best practices.

## Project-Specific Conventions

- Use Markdown/MDX for documentation pages. Example: `src/content/docs/guides/example.md`.
- Images for docs go in `src/assets/` and are referenced with relative paths.
- Use the Starlight integration for site structure and navigation.
- Commit messages should follow [Conventional Commits](https://www.conventionalcommits.org/) (enforced by `@commitlint/config-conventional`).

## Integration Points & Dependencies

- **Astro**: Static site generator.
- **@astrojs/starlight**: Documentation theme/integration.
- **@commitlint/config-conventional**: Commit message linting.
- See `package.json` for all dependencies.

## Examples

- To add a new guide: create `src/content/docs/guides/my-guide.md`.
- To add a sidebar entry: edit `astro.config.mjs` in the `sidebar` array.
- To embed an image: `![Alt text](../../assets/my-image.webp)` in your MDX.

## References

- [Starlight Docs](https://starlight.astro.build/)
- [Astro Docs](https://docs.astro.build/)

---

**For AI agents:**

- Prioritize updating documentation in `src/content/docs/`.
- Keep navigation and sidebar in sync with content changes.
- Follow project structure and conventions as described above.
