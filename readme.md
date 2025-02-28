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

# Install dependencies
pnpm install

# Start the development server
pnpm run start
```

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
