# Eslint with Drupal style

![ESLint Drupal Bundle JS logo](https://i.imgur.com/YyN3KrM.png)

ESLint bundled with the original Airbnb Style and prettier/recommended configs. Global installation is supported! No struggle with peer dependencies, easily integrates with your code editors.

See [airbnb/javascript] and [prettier/eslint] for more information.

See instructions for WebStorm, VSCode, Sublime Text and Atom

[airbnb/javascript]: https://github.com/airbnb/javascript
[prettier/eslint]: https://prettier.io/docs/en/eslint.html

## Installation

Install it globally:

```bash
npm install --global eslint-config-drupal-bundle
```

You can install it locally as well:

```bash
npm install --save-dev eslint-config-drupal-bundle
```

#### Setup your IDE / Editor:

[WebStorm](#user-content-webstorm)

[VSCode](#user-content-vscode)

[Sublime Text 3](#user-content-sublime-text-3)

[Atom](#user-content-atom)

## Usage

You can now run feature packed `eslint` from any directory:

```bash
eslint -v
```

Create `.eslintrc` file in your project. Setup your IDE / Editor. And be smart!

ES6, ES7, React, JSX, async/await - all new features supported by default 👍

## ESLint inside

You shouldn't add `eslint` to your dependencies. It's bundled with this package, just specify the path if you need.
Here is an example for `eslint-loader`:

```javascript
{
  loader: 'eslint-loader',
  options: {
    eslintPath: 'eslint-config-drupal-bundle/node_modules/eslint',
  }
},
```

## WebStorm

File ➤ Settings / Default Settings ➤ Languages and Frameworks ➤ JavaScript ➤ Code Quality Tools ➤ ESLint

![ESLint settings](https://i.imgur.com/YcmHkhx.png)

Global installation in not necessary for WebStorm, but it is handy for the "Default Settings".

## VSCode

1. Install this package globally (or locally)

2. Go to: *View -> Extension* or press `CTRL + SHIFT + X`

3. Search for [ESLint](https://github.com/Microsoft/vscode-eslint) extension, click it and press "Install" button

4. Press "Reload" button or reopen the editor

5. Go to: *File -> Preferences -> Settings*

   Add ESLint path to your workspace settings (do not use `~`):
    ```json
    {
      "eslint.nodePath": "/home/username/.nvm/versions/node/v10.5.0/lib/node_modules/eslint-config-drupal-bundle/node_modules/eslint",
    }
    ```

   Relative path for local installation:
    ```json
    {
      "eslint.nodePath": "node_modules/eslint-config-drupal-bundle/node_modules/eslint",
    }
    ```

7. Create `.eslintrc.js` file inside your working project root:
    ```js
    process.chdir(__dirname);

    module.exports = {
      root: true,
      parser: 'babel-eslint',
      parserOptions: {
        allowImportExportEverywhere: true,
        codeFrame: false
      },
      extends: [
        'drupal-bundle',
      ],
    };
    ```
    ![VSCode errors](https://i.imgur.com/sNL9w7V.png)

## Sublime Text 3

1. Install this package globally

2. Go to: *Preferences -> Package Control -> install package*

3. Install [SublimeLinter](https://packagecontrol.io/packages/SublimeLinter)

4. Install [SublimeLinter-contrib-eslint](https://packagecontrol.io/packages/SublimeLinter-contrib-eslint)

5. Run:
    ```bash
    npm bin -g
    ```
    ... and copy the path
6. Go to: *Tools -> SublimeLinter -> Open User Settings*

   Paste the path to NodeJS installation folder inside "paths" for your OS and save:
    ```json
    "paths": {
        "linux": [
            "~/.nvm/versions/node/v8.8.1/bin"
        ],
        "osx": [],
        "windows": ["%AppData%\\npm"]
    },
    ```
7. Create `.eslintrc` file inside your working project:
    ```json
    {
      "extends": ["drupal-bundle"]
    }
    ```

8. Restart Sublime Text

9. Go to *Tools -> SublimeLinter -> Lint this view*

10. You can switch to squiggly underline mark style from *Tools*. Have fun!

![Example](https://i.imgur.com/ShuWHXU.png)

## Atom

1. Install this package globally

2. Go to: *Edit -> Preferences -> Install*

3. Install [Linter](https://atom.io/packages/linter)

4. Install [linter-eslint](https://atom.io/packages/linter-eslint)

5. Run:
    ```bash
    npm prefix -g
    ```
    ... copy the prefix path
6. Go to: *Preferences -> Packages -> linter-eslint -> Settings*

   a) Check *"Use global ESLint installation"* option at the bottom

   b) Paste the prefix path to the field *"Global Node Installation Path"* and append:
   ```bash
   /lib/node_modules/eslint-config-drupal-bundle
   ```

    ![Example](https://i.imgur.com/6S9qYKk.png)

7. Create `.eslintrc` file inside your working project:
    ```json
    {
      "extends": ["drupal-bundle"]
    }
    ```

8. Press *`Ctrl + Shift + P` -> enter "lint" -> click "Linter:Lint"*

## Custom Config

Add your own rules to the `.eslintrc` file in your project folder.

## Credit

All credit to [doasync](https://github.com/doasync) and the original [eslint-config-airbnb-bundle](https://github.com/doasync/eslint-config-airbnb-bundle) of which this is a fork just adding extra config/dependencies of prettier to have function under Drupal 8.6+.
