# setup commands and options

```zsh
pnpm dlx create-single-spa --moduleType root-config
? Directory for new project .
? Which package manager do you want to use? pnpm
? Will this project use Typescript? Yes
? Would you like to use single-spa Layout Engine Yes
? Organization name (can use letters, numbers, dash or underscore) titanco
```

## Extending the root application

Adding New Microfrontends to Single-Spa Layout

To create a new microfrontend using the single-spa framework run:

```zsh
pnpm dlx create-single-spa
```

Add your application to the layout in microfrontend-layout.html. You can either:

Add it to a specific route: `<route path="/your-path"><application name="@titanco/your-app-name"></application></route>`
Add it as a permanent component (like a navbar): `<application name="@titanco/your-app-name"></application>`

Modify `src/titanco-root-config.ts` to register the new application.

Add an import map entry for your new microfrontend in `src/index.ejs` under the `isLocal` section. The format should be: `"@titanco/your-app-name": "//your-url"`
