# Web Boilerplates

## bboilerplate-tailwind - Static HTML with Tailwind CSS, Tailwind UI & PostCSS

### Prerequisites

1. VS Code (version >= `1.47`)
2. `dbaeumer.vscode-eslint` ESLint plugin (version >= `2.1.8`)
3. `esbenp.prettier-vscode` Prettier plugin (version >= `5.1.3`)
4. `ritwickdey.liveserver` Live Server plugin (version >= `5.6.1`)

### Getting started

Clone `web-boilerplates` repository

```
git clone https://github.com/neildobson-au/web-boilerplates.git
```

Navigate to `boilerplate-tailwind` folder

```
cd web-boilerplates/boilerplate-tailwind/
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

Build `output.css`

```
npm run build
```

In VS Code, right-click `index.html` and click Open with Live Server to preview.

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

Add default settings to `.prettierrc` file

```json
{
  "tabWidth": 2,
  "useTabs": false,
  "singleQuote": true
}
```

Install Tailwind, TailwindUI, PostCSS & Autoprefixer packages

```
npm i tailwindcss postcss-cli autoprefixer @tailwindcss/ui
```

Initialise Tailwind config file `tailwind.config.js`

```
npx tailwind init
```

Add plugins to `tailwind.config.js`

``` javascript
module.exports = {
  plugins: [require('@tailwindcss/ui')],
};
``` 

Create PostCSS config file `postcss.config.js`

```
touch postcss.config.js
```

Add plugins to `postcss.config.js`

``` javascript
module.exports = {
  plugins: [require('tailwindcss'), require('autoprefixer')],
};
```

Add `build` command to `package.json`

``` json
{
  "scripts": {
    "build": "postcss styles.css -o output.css"
  }
}
```

Reference output file in `index.html`

``` html
<head>
  <link rel="stylesheet" href="output.css" />
</head>
```
