# chicaga-tour

<a href="https://shipshape.io/"><img src="http://i.imgur.com/DWHQjA5.png" alt="Ship Shape" width="100" height="100"/></a>

**[chicaga-tour is a wrapper for VueJS with custom styles by Chicaga for Shepherd.js tour lib. Contact us for web app consulting, development, and training for your project.](https://shipshape.io/)**.

This is a Vue wrapper for the [Shepherd](https://github.com/shipshapecode/shepherd), site tour, library.

## Installation

### NPM

```bash
npm install chicaga-tour --save
```


Import styles to App.vue:

```css
@import '~chicaga-tour/dist/css/chicaga-tour.min.css';
```

When using with a module system, you must explicitly install chicaga-tour via Vue.use():

```js
import Vue from 'vue';
import ChicagaTour from 'chicaga-tour';

Vue.use(ChicagaTour);
```

### Constructor Function

```vue
<template>
  <div>
    Testing
  </div>
</template>

<script>
  export default {
    name: 'TourExample',
    mounted() {
      this.$nextTick(() => {
        const tour = this.$shepherd({
          useModalOverlay: true
        });

        tour.addStep({
          title: 'Welcome to Chicaga-tour',
          text: `Creating a tour is easy. too!\
          Just create a \`Tour\` instance, and add as many steps as you want.`,
          attachTo: {
            element: '.tour-example',
            on: 'bottom'
          },
          buttons: [
            {
              action() {
                return this.back();
              },
              classes: 'shepherd-button-secondary',
              text: 'Back'
            },
            {
              action() {
                return this.next();
              },
              text: 'Next'
            }
          ],
          id: 'creating'
        });

        tour.start();
      });
    }
  };
</script>
```


