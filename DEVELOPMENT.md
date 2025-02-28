# Development Guide

This document provides instructions for setting up and extending the application.

## Initial Setup

The root application was created with:

```bash
pnpm dlx create-single-spa --moduleType root-config
? Directory for new project .
? Which package manager do you want to use? pnpm
? Will this project use Typescript? Yes
? Would you like to use single-spa Layout Engine Yes
? Organization name (can use letters, numbers, dash or underscore) titanco
```

## Creating a New Microfrontend

To create a new microfrontend:

```bash
pnpm dlx create-single-spa
```

Follow the prompts to configure your new microfrontend.

## Adding a Microfrontend to the Root Application

After creating a new microfrontend, you need to integrate it with the root application:

1. **Add to Layout**

   Edit `packages/shell/titanco-root-app/src/microfrontend-layout.html` and add your application:

   ```html
   <!-- For route-specific microfrontend -->
   <route path="/your-path">
     <application name="@titanco/your-app-name"></application>
   </route>

   <!-- For permanent components like navigation -->
   <application name="@titanco/your-app-name"></application>
   ```

2. **Add to Import Map**

   Edit `packages/shell/titanco-root-app/src/index.ejs` and add your microfrontend to the import map:

   ```javascript
   {
     "imports": {
       "@titanco/root-config": "//localhost:9000/titanco-root-config.js",
       "@titanco/your-app-name": "//localhost:your-port/your-app-name.js"
     }
   }
   ```

3. **Import in Root Config**

   If needed, update `packages/shell/titanco-root-app/src/titanco-root-config.ts` to import your microfrontend:

   ```typescript
   import('@titanco/your-app-name');
   ```

## Development Workflow

1. **Start the Root Application**

   ```bash
   cd packages/shell/titanco-root-app
   pnpm start
   ```

2. **Start Your Microfrontend**

   ```bash
   cd packages/microfrontends/your-microfrontend
   pnpm serve
   ```

3. **Access the Application**

   Open your browser to the URL displayed in the console (typically <http://localhost:9000>)

## Code Quality

This project uses:

- **ESLint** for static code analysis
- **Prettier** for code formatting

To lint and format your code:

```bash
pnpm run lint
```

## Testing

Each microfrontend should include its own tests. Run tests with:

```bash
cd packages/microfrontends/your-microfrontend
pnpm test:unit
```
