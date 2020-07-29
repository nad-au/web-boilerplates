# Web Boilerplates

## boilerplate-eslint-prettier - Basic linting & prettier code formatting support in VS Code

### Prerequisites

1. VS Code (version >= `1.47`)
2. `dbaeumer.vscode-eslint` ESLint plugin (version >= `2.1.8`)
3. `esbenp.prettier-vscode` Prettier plugin (version >= `5.1.3` )

### Getting started

Clone `web-boilerplates` repository

```
git clone https://github.com/neildobson-au/web-boilerplates.git
```

Navigate to `eslint` folder

```
cd web-boilerplates/boilerplate-eslint-prettier/
```

Install packages

```
npm install
```

Start VS Code

```
code .
```

Edit `settings.json` to set:

1. Enable auto-fixing lint errors on save.
2. Set the editor's default formatter to prettier

```json
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "editor.defaultFormatter": "esbenp.prettier-vscode"
}
```

### Testing

Open `test.js` and inspect errors. Hit `ctrl-s` to save file and auto-fix linting errors. \
Open `index.html` and hit `ctrl-s` to format html.

### Template set-up

The following describes the steps to generate this boilerplate template.

Initialise project

```
npm init -y
```

Install ESLint package

```
npx eslint --init
```

Set the following

```
✔ How would you like to use ESLint? · style
✔ What type of modules does your project use? · esm
✔ Which framework does your project use? · none
✔ Does your project use TypeScript? · No / Yes
✔ Where does your code run? · browser
✔ How would you like to define a style for your project? · guide
✔ Which style guide do you want to follow? · standard
✔ What format do you want your config file to be in? · JavaScript
```

Install Prettier packages and ESLint / prettier plugins

```
npm i -D prettier eslint-config-prettier eslint-plugin-prettier
```

Add `plugin:prettier/recommended` as the last extension in `.eslintrc.js` file

```javascript
module.exports = {

  extends: ['standard', 'plugin:prettier/recommended'],

};
```

Create `.prettierrc` file

```
touch .prettierrc
```

Add default settings

``` json
{
  "tabWidth": 2,
  "useTabs": false,
  "singleQuote": true
}
```