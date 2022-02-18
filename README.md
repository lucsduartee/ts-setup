# My initial setup for Typescript

1. Generate `.gitignore` file [here](https://www.toptal.com/developers/gitignore)

2. Initializing _project_
    ```bash
      npm init -y
    ```
3. Install _Typescript_ as dev dependency
    ```bash
      npm i typescript -D
    ```
4. Add Code Runner extension (_Optional_)
    - Create `.vscode` with content below:
      ```json
        // settings.json
        {
          "code-runner.executorMap": {
          "typescript": "clear && npx ts-node --files",
          }
        }
      ```
5. Install ESLint
    ```bash
      npm -i eslint -D
      npm i @typescript-eslint/eslint-plugin @typescript-eslint/parser -D
    ```
6. Create `eslintrc.js` with content:
    ```js
      module.exports = {
        env: {
          browser: true,
          es6: true,
          node: true,
        },
        extends: [
          'eslint:recommended',
          'plugin:@typescript-eslint/eslint-recommended',
          'plugin:@typescript-eslint/recommended',
          'plugin:prettier/recommended',
        ],
        globals: {
          Atomics: 'readonly',
          SharedArrayBuffer: 'readonly',
        },
        parser: '@typescript-eslint/parser',
        parserOptions: {
          ecmaVersion: 11,
          sourceType: 'module',
        },
        plugins: ['@typescript-eslint'],
        rules: {},
      };
    ```
7. Install Prettier
    ```bash
      npm i prettier eslint-config-prettier eslint-plugin-prettier -D
    ```
8. Create `prettierrc.js` with content:
    ```js
      module.exports = {
        semi: true,
        trailingComma: 'all',
        singleQuote: true,
        printWidth: 90,
        tabWidth: 2,
      }
    ```
9. Run
    ```bash
      npx tsc --init
    ```
10. Generate `.editorconfig` on _VSCode_.
