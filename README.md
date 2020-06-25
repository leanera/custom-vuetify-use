# Custom Vuetify Usage

## Intro

We already created our [component library](https://github.com/leanera/custom-vuetify), so it's time to use it in a real app, like in this sample.

## Main parts

| Module                                                        | Version    |
| ---                                                           | ---        |
| [Vue](https://github.com/vuejs/vue)                           | 2.6.11     |
| [@vue/cli](https://github.com/vuejs/vue-cli)                  | 4.4.4      |
| [vuetify](https://github.com/vuetifyjs/vuetify)               | 2.2.11     |

## Vue Configuration

For our component library, we use Vue with following features/configurations:
* Babel
* Typescript
* vuex
* vue-router
* CSS Pre-processors (Sass/SCSS)
* Linter (ESLint + Prettier)
* class-style component syntax

## Build & Use

### Commands

`npm run build` - build your app  
`npm run serve` - serve your app locally  

### Integration

We created this project via Vue-CLI with settings listed above, executed `vue add vuetify` to setup and configure vuetify.

Also, we already built our component library and linked it locally.

If you now run `npm run serve`, you should see a basic vuetify app, but we still want to use our components.

So simply add a new `.ts` file to the plugins directory with following content:

```typescript
// ./src/plugins/lea-components.ts

import Vue from "vue";
import Components from '@leanera/custom-vuetify';
import '@leanera/custom-vuetify/dist/custom-vuetify.css'

Vue.use(Components);
```

*make sure to change the package name to match your library*

Import your plugin in your `main.ts`:

```typescript
// ./src/main.ts

// ...
import "./plugins/lea-components";
import vuetify from "./plugins/vuetify";

new Vue({
  router,
  store,
  vuetify,
  render: (h) => h(App),
}).$mount("#app");

```

That's it! Now you can use your created components just like any other (see `./src/views/Login.vue`).
