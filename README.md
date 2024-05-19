# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
   parserOptions: {
    ecmaVersion: 'latest',
    sourceType: 'module',
    project: ['./tsconfig.json', './tsconfig.node.json'],
    tsconfigRootDir: __dirname,
   },
```

- Replace `plugin:@typescript-eslint/recommended` to `plugin:@typescript-eslint/recommended-type-checked` or `plugin:@typescript-eslint/strict-type-checked`
- Optionally add `plugin:@typescript-eslint/stylistic-type-checked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and add `plugin:react/recommended` & `plugin:react/jsx-runtime` to the `extends` list


## Continous Development & Delivery

For Continous development this project is using GitHub reusable actions with selfhosted runner.
Branching strategy is GitFlow
   1) Tag from main branch - Prod 
   2) main branch - Preprd
   3) Develop branch - Dev
   4) QA branch - QA 

For every PR open it will run Snyk, Sonarqube and Label check Workflows and Once PR is merge it will build the code and upload artifacts to GitHub artifacts
For every non Prod release creation is automated using Workflows and for every PR merge new GH release will create


Continous Deployment 
-- 
Currently this system hosted on Azure(Moved from orginally hosted AWS due to high pricing). 
Continous Deployment workflow is not used yet
