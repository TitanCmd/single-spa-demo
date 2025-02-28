# Single-SPA Demo Application

This project demonstrates a microfrontend architecture using [single-spa](https://single-spa.js.org/). It showcases how to build a complex application with multiple isolated frontend components that can be developed, tested, and deployed independently.

## Overview

The application is structured as a monorepo with multiple packages:

- **Shell**: Contains the root application that orchestrates all microfrontends
- **Microfrontends**: Individual frontend applications that are composed together

## Getting Started

```bash
# Clone the repository
git clone <repository-url>

# Install dependencies for all packages
pnpm run setup

# Start all microfrontends and the root application
pnpm start
```

## Streamlined Development Workflow

This project uses a streamlined workflow to make it easier to work with multiple microfrontends:

- **`pnpm run setup`**: Installs dependencies for all packages
- **`pnpm run start`**: Starts both the root application and all microfrontends concurrently
- **`pnpm run build`**: Builds all packages
- **`pnpm run test`**: Runs tests for all packages
- **`pnpm run lint`**: Lints all packages
- **`pnpm run format`**: Formats all packages

This approach allows you to manage the entire application from the top level without having to run commands in individual package directories.

I facilitated this using PNPM workspaces. But this could also be done using nx or similar tool.

You also still have the control over each microfrontend by running `pnpm install` and `pnpm run start` in the respective microfrontend directory.

## Project Structure

```
single-spa-demo/
├── packages/
│   ├── shell/
│   │   └── titanco-root-app/     # Root application that hosts microfrontends
│   └── microfrontends/
│       └── titanco-navigation/   # Navigation component microfrontend
├── ARCHITECTURE.md               # Architectural decisions documentation
├── DEVELOPMENT.md                # Development workflow and setup instructions
└── README.md                     # This file
```

## Documentation

- [Architecture](./ARCHITECTURE.md) - Architectural decisions and patterns
- [Development](./DEVELOPMENT.md) - Development workflow and setup instructions

## Microfrontends

Each microfrontend is a standalone application that can be developed and deployed independently:

- **titanco-navigation**: Navigation component built with Vue.js

See the README in each microfrontend directory for specific instructions.

## Running Individual Microfrontends

If you need to work on a specific microfrontend, you can use pnpm's filter feature:

```bash
# Start only the navigation microfrontend
pnpm --filter @titanco/titanco-navigation serve:standalone

# Start only the root application
pnpm --filter @titanco/root-config start
```
