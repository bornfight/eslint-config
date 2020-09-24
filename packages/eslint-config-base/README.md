# @bornfight/eslint-config-base

> Base ESLint config rules, independent of environment and frameworks.

## Install

Using npm:

```sh
npm install --save-dev @bornfight/eslint-config-base
```

or using yarn:

```sh
yarn add @bornfight/eslint-config-base --dev
```

## Vue implementation

It is also possible to use this package in your Vue project. There is no separate package to handle this, since it's a better idea to let Vue's [cli-eslint-plugin](https://cli.vuejs.org/core-plugins/eslint.html) to worry about the hard work.

The first thing you must do (if you haven't already) is to install `@vue/cli-plugin-eslint`. Install this with Vue's CLI or your terminal.

After you've installed the plugin and this package, open your .eslintrc.js file and add

```
        "@bornfight/eslint-config-base"
```

in your "extends" array. Something like this

```
extends: [
        "prettier",
        "plugin:vue/essential",
        "eslint:recommended",
        "plugin:vue/base",
        "@vue/typescript/recommended",
        "@vue/prettier",
        "@vue/prettier/@typescript-eslint",
        "@bornfight/eslint-config-base"
    ]
```

That's pretty much it, now the CLI plugin will handle linting your .vue, .js and .ts files and apply all of your rules.

### Issues

There is an issue that may occur when you use this package in Vue. Since there's a lot of rules being applied, some might clash with one another.
For instance, [tab width in prettier](https://prettier.io/docs/en/options.html#tab-width) and [indent in eslint](https://eslint.org/docs/rules/indent). If errors like these happen, just make sure to have both of the rules apply the same value. You can also turn off one of the option's reporting, so you just get one error.
