# Key architectural decision register

Moved to a monorepo type structure.
Originally this was the repo just for the root-app and I was going to have the repo's separate as you typically would in a single-spa microfrontend setup, but with time constraints and ease of sharing I opted for monorepo type structure.

Each folder in packages/** is a separate microfrontend.

Normally with separate repo's you get separate deploys easily through CI/CD on each repo, plus no pollution of PR's etc.

## Frontend framework

- Vue ✅
- React ❌
- Svelte ❌

Vue chosen for speed and my experience

## DX Environment

- Added prettier
- Added eslint
- Added fix on save vscode settings for this workspace
- Use strict typescript compiler options
