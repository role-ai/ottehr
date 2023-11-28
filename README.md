# Ottehr

## Repository Structure

This repository uses a monorepo structure. Each package has its own code in its respective folder in [`packages/`](./packages/).

- `app` - The static frontend website that patients use to join their telehealth visit and providers use to answer.
- `zambdas` - The application's back end endpoints, deployed on the zapEHR platform.

Each package has its own README explaining in more detail its purpose, as well as how to run locally and deploy (if applicable).

## First Time Setup

### Node

- Install [nvm](https://github.com/nvm-sh/nvm#installing-and-updating).
- Use nvm to install node 18: `nvm install 18`.
- Use nvm to make node 18 your default node: `nvm alias default 18`.

Upon successful installation, verify the setup by executing the following command: `node -v`. If the installation was successful, this command should provide the version of Node currently installed

### ESLint

To enhance code readability, we maintain a robust ESLint configuration that ensures strict adherence to coding standards. For an optimal coding experience with real-time linting feedback, we highly recommend using Visual Studio Code (VSCode), which offers an outstanding live linting environment.

To get linting in VSCode:

1. Install the [ESLint Extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint).
2. Always open the repo from its root. This allows the extension to detect the `.eslintrc.json` file which specifies the linter configuration.
3. (Optional) Use the [VSCode workspace](./.vscode/Ottehr.code-workspace) for a helpful alternative organization of the project in the VSCode 'Explorer', which most developers find useful. This can be opened in 2 ways:
   1. Open [the file](./.vscode/Ottehr.code-workspace) in VS Code. Click on the "Open Workspace" button in the bottom-right.
   2. `code .vscode/Ottehr.code-workspace`

### Installing `pnpm`

The easiest way to get started is to use the [brew](https://brew.sh/) command:

*If Homebrew is not yet installed on your system, you can easily set it up [here](https://brew.sh/).*

```bash
brew install pnpm
```

Otherwise, you can install it onto your machine using the [documentation](https://pnpm.io/installation).

### Getting started

Run `pnpm i` at the root level to install dependencies for all packages in the monorepo. Then run `pnpm start` to start all packages locally.

## Scripts

```sh
pnpm <script name>
```

If a script is environment specific, use:

```sh
pnpm <script name>:<env>
```

### `build`

Builds all packages using the [build script](./scripts/build.sh).

### `lint`

Lints all packages using [ESLint](https://eslint.org/).

### `start`

Environment specific: `local`, `dev`, `dev2`, `testing`, `staging`.

Starts all packages. If the env is excluded, [defaults to local](#getting-started).

### `update`

Interactively updates all dependencies to their latest versions, respecting ranges specified in `package.json`.