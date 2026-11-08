# Next.js Clean Starter Template

An optimized, lightweight production-ready starter template for building modern web applications using **Next.js 16**, **Tailwind CSS v4**, and **TypeScript**. This setup is fully configured for **100% offline development** using `pnpm`.

## 📐 Architecture

This project follows **Feature-Driven Architecture (FDA)** principles to ensure strict code isolation, maintainability, and scalability. All core logic lives inside the `src/` directory, broken down into standardized layers:

- `src/app/` — Global configurations, providers, styles, and Next.js App Router layout/page definitions.
- `src/pages/` — Composition layer for full-screen application views.
- `src/widgets/` — Self-contained, structural UI blocks (e.g., `Header`, `Footer`, `Sidebar`).
- `src/features/` — User interactions that bring business value (e.g., `AuthForm`, `LanguageSwitcher`).
- `src/entities/` — Core business models, components, and state (e.g., `UserCard`, `ProductRow`).
- `src/shared/` — Reusable, decoupled assets, UI primitives (`shared/ui`), API clients, and custom React hooks.

## 🛠 Offline Setup & Usage

Since all modules are pre-cached in your local global store (`~/development/pnpm-store`), you can spin up brand-new projects completely without an internet connection.

### Creating a New Project from this Template:

1. Duplicate this template directory:
   ```bash
   cp -R next-clean-template my-new-project
   ```
2. Navigate into the new folder and mount the offline dependencies instantly:
   ```bash
   cd my-new-project
   pnpm i --offline
   ```

## ⚡ Available CLI Scripts

All commands must be executed from the project root:

- `pnpm dev` — Starts the local Next.js development server with Turbopack enabled on [http://localhost:3000](http://localhost:3000).
- `pnpm build` — Compiles the application for production deployment.
- `pnpm start` — Starts the production Node.js server.
- `pnpm lint` — Runs ESLint checks to enforce clean code standards.

## 🔗 Absolute Imports Configuration

Path aliases are pre-configured in `tsconfig.json`. You can cleanly import your codebase modules using the `@/*` absolute paths from anywhere:

```typescript
import { Button } from "@/shared/ui";
import { Header } from "@/widgets/header";
```
