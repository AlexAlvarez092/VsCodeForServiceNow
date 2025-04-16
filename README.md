# Personal VS Code Configuration

This repository contains my personal configuration for working with JavaScript/TypeScript and ServiceNow in Visual Studio Code. It includes strict linting and formatting rules, as well as configuration for the **iKosak Sync Now** extension.

## Included Files

### `.eslintrc.json`
Detailed ESLint configuration to enforce consistent coding style and prevent common mistakes. Key features:
- Stroustrup brace style
- Max line length: 115 characters
- Preference for `const` and arrow functions
- Rules to avoid ambiguity and poor practices
- Predefined global variables for ServiceNow development (e.g., `g_form`, `gs`, `GlideRecord`, etc.)

### `.prettierrc.json`
[Prettier](https://prettier.io/) configuration to maintain clean and readable code:
- Single quotes
- No trailing commas
- Max line width: 120 characters
- Tab width: 4 spaces
- `arrowParens: avoid`
- Semicolons enabled

### `ikosak.yaml`
Configuration file for the [iKosak Sync Now](https://marketplace.visualstudio.com/items?itemName=ikostrikov.ikosak-sync-now) VS Code extension. It allows syncing ServiceNow entities directly from your codebase. It defines:
- Target folders per entity type (Business Rules, Client Scripts, UI Actions, etc.)
- Which fields to sync for each table
- Folder structure using `subDirPattern`
- Custom encoded queries for filtering by `sys_scope`, name prefixes, etc.

This setup is especially suited for instances using custom scopes (`x_`) and custom tables (`u_`).

## Usage

1. Install the following VS Code extensions:
   - ESLint
   - Prettier
   - iKosak Sync Now

2. Ensure your workspace respects the ESLint and Prettier rules. You can also include these scripts in your `package.json` if you're working on a Node.js project:

   ```json
   "scripts": {
     "lint": "eslint .",
     "format": "prettier --write ."
   }

## Requirements

   - Node.js and npm installed (for linting and formatting)
   - Active ServiceNow instance if using iKosak Sync Now