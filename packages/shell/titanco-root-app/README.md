# Root Application Shell

This is the shell application that hosts and orchestrates all microfrontends in the single-spa demo.

## Features

- Single-SPA Layout Engine integration
- Import map configuration for microfrontends
- TypeScript support

## Development

### Project setup

```zsh
pnpm install
```

### Compiles and hot-reloads for development

```zsh
pnpm start
```

### Compiles and minifies for production

```zsh
pnpm run build
```

### Lints and fixes files

```zsh
pnpm run lint
```

## Adding Microfrontends

The root application is responsible for:

1. Defining the layout in `src/microfrontend-layout.html`
2. Configuring import maps in `src/index.ejs`
3. Loading microfrontends through the single-spa layout engine

See the [Development Guide](../../../DEVELOPMENT.md) for detailed instructions on adding new microfrontends.

## Configuration

### Webpack Configuration

The webpack configuration can be customized in `webpack.config.js`.

### Layout Configuration

The layout is defined in `src/microfrontend-layout.html` using the single-spa layout engine.
