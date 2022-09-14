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
@import '~chicaga-tour/dist/chicaga-tour.min.css';
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
  <div class='tour-example'>
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
          title: 'Реферальная программа',
          text: 'При клике на аватарку или ФИО вы попадете в <b>личный кабинет</b>,где сможете изменить свои данные.\
          При клике на стрелочку появится меню где расположены кнопки для связи с куратором,\
          опционально с преподавателем, <i>зависит от тарифа</i>, так же настройки личного кабинета.',
          attachTo: {
            element: '.tour-example',
            on: 'bottom'
          },
          buttons: [
            {
              action() {
                return this.cancel();
              },
              classes: 'shepherd-button-secondary',
              text: 'Пропустить'
            },
            {
              action() {
                return this.next();
              },
              text: 'Далее'
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


