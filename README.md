# Vue 3 + Vite

This template should help get you started developing with Vue 3 in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Configuration with ESLint and Prettier

1. Create Vue3 project using Vite

   ```
   npm create vite@latest
   ```

2. Install Prettier

   ```
   npm install --save-dev --save-exact prettier
   ```

   And create a config file for prettier:

   ```
   echo {}> .prettierrc.json
   ```

3. Install ESLint

   ```
   npm install --save-dev eslint eslint-plugin-vue
   ```

   And configure ESLint by creating a .eslintrc.js file:

   ```js
   module.exports = {
     env: {
       node: true,
     },
     extends: ['eslint:recommended', 'plugin:vue/vue3-recommended'],
     rules: {
       // override/add rules settings here, such as:
       // 'vue/no-unused-vars': 'error'
     },
   }
   ```

4. Turn off ESLint's formatting rules that would conflict with Prettier

   ```
   npm install --save-dev eslint-config-prettier
   ```

   And register the config in .eslintrc.js file under extends:

   ```js
   extends: [
    'eslint:recommended',
    'plugin:vue/vue3-recommended',
    'prettier',
   ],
   ```

5. Add commands to scripts in package.json

   ```json
   "scripts":{
     //...
     "lint": "eslint --ext .js,.vue --ignore-path .gitignore --fix src",
     "format": "prettier .  --write"
   }
   ```

6. Set up ESLint and Prettier with VS Code

   .vscode/settings.json

   ```json
   {
     "editor.defaultFormatter": "esbenp.prettier-vscode",
     "editor.formatOnSave": true
   }
   ```

7. Update Prettier config

   .prettierrc.json

   ```json
   {
     "singleQuote": true,
     "trailingComma": "es5",
     "tabWidth": 2,
     "semi": false,
     "arrowParens": "avoid"
   }
   ```

Reference:

- [Vite](https://vitejs.dev/)
- [Prettier](https://prettier.io/)
- [ESLint](https://eslint.org/)
- [ESLint and Prettier with Vite and Vue.js 3](https://vueschool.io/articles/vuejs-tutorials/eslint-and-prettier-with-vite-and-vue-js-3/)

## Configuration with Import Alias

vite.config.js

```js
import path from 'path'

export default defineConfig({
  resolve: {
    alias: {
      '@': path.resolve(__dirname, './src'),
    },
  },
})
```

jsconfig.json

```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}
```
