# Architecture

This document outlines the key architectural decisions made for this project.

## Monorepo Structure

Originally this was intended to be separate repositories for each microfrontend, which is typical in a single-spa setup. However, for ease of development and sharing, a monorepo structure was chosen.

**Benefits:**

- Simplified development workflow
- Easier sharing of code and dependencies
- Simplified demonstration

**Trade-offs:**

- In a production environment, separate repositories would provide:
  - Independent deployment pipelines
  - Cleaner PR workflows
  - Better team isolation

## Frontend Framework Selection

- **Vue.js ✅** - Chosen for speed of development and developer experience
- **React ❌** - Not selected for this demonstration
- **Svelte ❌** - Not selected for this demonstration

## Single-SPA Layout Engine

The project uses the single-spa Layout Engine for several reasons:

- Declarative routing
- Easier scaling of microfrontends
- Better developer experience by eliminating manual mounting/unmounting
- Good integration with Vue.js

## Microfrontend Structure

The microfrontends are structured to demonstrate the architectural pattern rather than implementing a full-featured application:

- **Navigation** - A standalone navigation component
- **Main Content** - Content areas that can be swapped based on routes

This demonstrates how microfrontends can be separated at various isolation points:

1. UI components (like navigation/header)
2. Feature-based modules (like reporting, dashboard, analytics)
3. Or a combination of both approaches

## Development Environment

The development environment includes:

- **Prettier** - For consistent code formatting
- **ESLint** - For static code analysis
- **TypeScript** - With strict compiler options for type safety
- **VSCode Settings** - Configured for this workspace with fix-on-save
