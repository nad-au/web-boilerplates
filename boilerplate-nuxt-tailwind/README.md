# Web Boilerplates

## boilerplate-nuxt-tailwind - Nuxt app with Nuxt Content, Tailwind CSS, Tailwind UI & Tailwind Typography

### Prerequisites

1. VS Code (version >= `1.47`)
2. `dbaeumer.vscode-eslint` ESLint plugin (version >= `2.1.8`)
3. `esbenp.prettier-vscode` Prettier plugin (version >= `5.1.3`)

### Getting started

Clone `web-boilerplates` repository

```
git clone https://github.com/neildobson-au/web-boilerplates.git
```

Navigate to `boilerplate-nuxt-tailwind` folder

```
cd web-boilerplates/boilerplate-nuxt-tailwind/
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

Preview

```
npm run dev
```

### Template set-up

The following describes the steps to generate this boilerplate template.

Create nuxt project

```
npx create-nuxt-app boilerplate-nuxt-tailwind
```

Set the following

```
? Project name: boilerplate-nuxt-tailwind
? Programming language: JavaScript
? Package manager: Npm
? UI framework: Tailwind CSS
? Nuxt.js modules: Content
? Linting tools: ESLint, Prettier
? Testing framework: None
? Rendering mode: Universal (SSR / SSG)
? Deployment target: Static (Static/JAMStack hosting)
? Development tools: jsconfig.json (Recommended for VS Code if you're not using
typescript)
```

Add default settings to `.prettierrc` file

```json
{
  "semi": false,
  "singleQuote": true,
  "tabWidth": 2,
  "useTabs": false
}
```

Run build to generate `tailwind.config.js` & `assets/css/tailwind.css` files

```
npm run build
```

Install [Tailwind UI](https://tailwindui.com/) package

```
npm i @tailwindcss/ui
```

Add plugins to `tailwind.config.js`

```javascript
module.exports = {
  plugins: [require('@tailwindcss/ui')],
}
```

Update `nuxt.config.js` to reference [Inter](https://rsms.me/inter/) typeface family in the page's head element

```javascript
export default {
  head: {
    link: [{ rel: 'stylesheet', href: 'https://rsms.me/inter/inter.css' }],
  },
}
```

Update `tailwind.config.js` to set the theme's font to [Inter](https://rsms.me/inter/)

```javascript
const defaultTheme = require('tailwindcss/defaultTheme')

module.exports = {
  theme: {
    extend: {
      fontFamily: {
        sans: ['Inter var', ...defaultTheme.fontFamily.sans],
      },
    },
  },
}
```

Install [Tailwind Typography](https://github.com/tailwindlabs/tailwindcss-typography) plugin

```
npm install @tailwindcss/typography
```

Update `tailwind.config.js` to reference the plugin

```javascript
const defaultTheme = require('tailwindcss/defaultTheme')

module.exports = {
  plugins: [require('@tailwindcss/typography')],
}
```
