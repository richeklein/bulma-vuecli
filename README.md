# Using Bulma in a Vue-CLI 3 App
This is an example app that demonstrates using Bulma with a Vue CLI 3 generated application.

## Building Locally from the Existing Code
You can build the application locally by running:
```bash
$ yarn install

$ yarn run serve  # Compiles and hot-reloads for development

$ yarn run build  # Compiles and minifies for production
```

## Building your own Vue + Bulma Application Using Vue-CLI 3
Below is a summary of how to build a Bulma + VueJS app from scratch using the excellent Vue CLI. You will need to have `vue-cli` and `yarn` or `npm` installed locally to continue.

### Create the app template using Vue CLI and install dependencies
```bash
$ vue create bulma-vuecli

$ cd bulma-vuecli

# install sass and the webpack sass loader
$ yarn add --dev sass-loader sass

# install Bulma dependency
$ yarn add --dev bulma
```

### Test the app
```bash
$ yarn run serve
```

### Including Bulma Sass
Vue CLI 3 uses Webpack to bundle your assets (styles, images, js, etc.). [Check the VueJS docs for details](https://cli.vuejs.org/guide/css.html#referencing-assets). Although there are multiple ways to include Bulma in your project using Webpack, here's a simple approach that works well:

#### Create a src/assets/sass/main.scss file to manage all Bulma and Sass imports
Your `main.scss` is the entry point for all of your Sass files--including Bulma. It's a common practice in Sass to have a single entry point to manage all of your Sass imports. You can further structure your Sass code into subfolders by component, utility, functions, variables, etc. The [Bulma source code](https://github.com/jgthms/bulma) is a very good  reference for ideas on structuring your own Sass.

```bash
$ cd src/assets

$ mkdir sass

$ touch main.scss
```

#### Add Bulma, custom Sass styles, and Bulma variable customizations to main.scss
```scss
/* Custom Fonts */
@import url('https://fonts.googleapis.com/css?family=Open+Sans|Libre+Baskerville');

/* Custom Variables and Functions*/
@import 'variables';

/* Uncomment to import the entire Bulma framework */
// @import '~bulma/bulma';

/* Import selected Bulma Sass */
/* Remove these if you import the entire Bulma framework above */
@import "~bulma/sass/utilities/_all.sass";
@import "~bulma/sass/base/_all.sass";
@import "~bulma/sass/grid/_all.sass";
@import "~bulma/sass/elements/button.sass";
@import "~bulma/sass/elements/container.sass";
@import "~bulma/sass/elements/title.sass";
@import "~bulma/sass/layout/section.sass";
@import "~bulma/sass/components/card.sass";
```

#### Import main.scss into your main.js
vue-cli generated a `main.js` file for your application that is used as the entry point for your Vue application. The file loads VueJS and your root component (`App.vue`) and is a good place to import global styles (such as Bulma). For component-specific styles, you can embed the Sass directly in your the component using VueJS [Single File Components](https://vuejs.org/v2/guide/single-file-components.html).

Add `import './assets/sass/main.scss'` to your `main.js` file. Your updated `main.js` files should look similar to this:
```js
import Vue from 'vue'
import App from './App.vue'
import './assets/sass/main.scss'

Vue.config.productionTip = false

new Vue({
  render: h => h(App),
}).$mount('#app')
```

### Build Your App!
Run `yarn run serve` during development to automatically compile all of your Sass and JS locally and hot reload your page. You can now use Bulma styles and components throughout your components and templates!

When you're ready to deploy to production, be sure to run `yarn run build` to minify your asset bundle. See the [VueJS Deployment docs](https://cli.vuejs.org/guide/deployment.html) to learn more.