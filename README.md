# Vue 3 Introduction Workshop

In this introduction workshop I will learn to do the following things:

- Learn Essential Vue Concepts
- Learn Components, Directives, and Options API
- Learn the Composition API and Built-in Components
- Learn Tooling in the Vue Ecosystem
- Learn Routing with Vue Router
- Learn State Management with Pinia

## Instructor Information

Ben Hong is a Vue.js Core Team member and a Senior Staff Developer Experience (DX) Engineer at Netlify. He is also a developer / psychologist / educator hybrid who is passionate about creating products that help to empower people with new skills and knowledge regardless of their background.

You can learn more about his work at https://www.bencodezen.io.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Type Support for `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) to make the TypeScript language service aware of `.vue` types.

## Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Type-Check, Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```

## Notes To Self

- Build tools won't do anything to the `public` directory. No asset optimization or anything like that, it's simply bundled and served as is
- If we scaffold a project with the language set to TS, we can allow JS by adding `allowJs: true` to the `compilerOptions` of the `tsconfig.app.json` file
