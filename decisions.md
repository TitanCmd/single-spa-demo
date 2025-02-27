# Key decisions register

## Frontend framework

- Vue ✅
- React ❌

Vue chosen for speed and developer experience

## Setup

pnpm dlx create-single-spa --moduleType root-config

using single-spa Layout engine: Yes

- Speed and declarative routing
- Easier scaling
- Better DX, not needing to manually mount and unmount micro-frontends
- Works well with vue

## Microfrontend layout

- Single-spa layout engine
- Layout file: `src/microfrontend-layout.html`

## DX Environment

- Added prettier
- Added eslint
- Added fix on save vscode settings for this workspace
- Use strict typescript compiler options
