# Navigation Microfrontend

This is a Vue.js-based microfrontend that provides the navigation component for the single-spa demo application.

## Features

- Responsive navigation menu
- Integration with single-spa
- Built with Vue.js and TypeScript

## Development

### Project setup

```zsh
pnpm install
```

### Compiles and hot-reloads for development

```zsh
pnpm run serve
```

### Compiles and minifies for production

```zsh
pnpm run build
```

### Run your unit tests

```zsh
pnpm run test:unit
```

### Lints and fixes files

```zsh
pnpm run lint
```

## Integration with Root Application

This microfrontend is integrated with the root application through:

1. Import map in the root application's `index.ejs`
2. Layout configuration in the root application's `microfrontend-layout.html`

See the [Development Guide](../../../DEVELOPMENT.md) for more details on how microfrontends are integrated.

## Customization

### Vue Configuration

See [Vue CLI Configuration Reference](https://cli.vuejs.org/config/).
