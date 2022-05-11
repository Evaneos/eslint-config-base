# ESLint (and Prettier) config

This package provides Evaneos' configs for front projects.

-   `.eslintrc` as an extensible shared config.
-   `.prettierrc` as an importable file

## What it does

This setup lints and formats your JavaScript code based on Evaneos practices. Feel free to override the rules that make sense for you.

## Installing

1.  In your project folder, run:

    ```bash
    npm i -D @evaneos/eslint-config
    npx install-peerdeps --dev @evaneos/eslint-config
    ```

2.  You will see several dependencies were installed. Now, create (or update) a `.eslintrc` file with the following content:

    ```
    {
       "extends": [
          "@evaneos/eslint-config"
       ]
    }
    ```

    **If you extend anything else, always end up as following:**

    ```
    {
       "extends": [
          "@evaneos/eslint-config",
          ...,
          "@evaneos/eslint-config/prettier",
       ]
    }
    ```

3.  Add prettier config to your `package.json`

    ```
    {
       "prettier": "@evaneos/eslint-config/.prettierrc.js"
    }
    ```

    If you want to override it, you'll have to spread the config into a `.prettierrc.js` file instead, eg:

    ```js
    module.exports = {
        ...require('@evaneos/eslint-config/.prettierrc.js'),
        semi: false,
    };
    ```

<!-- 4. Copy the .tsconfig file from this repository into your project folder -->
