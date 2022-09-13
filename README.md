# chicaga-tour

<a href="https://shipshape.io/"><img src="http://i.imgur.com/DWHQjA5.png" alt="Ship Shape" width="100" height="100"/></a>

**[chicaga-tour is built and maintained by Ship Shape. Contact us for web app consulting, development, and training for your project](https://shipshape.io/)**.

[![npm version](https://badge.fury.io/js/chicaga-tour.svg)](http://badge.fury.io/js/chicaga-tour)
![Download count all time](https://img.shields.io/npm/dt/chicaga-tour.svg)
[![npm](https://img.shields.io/npm/dm/chicaga-tour.svg)]()
[![Build Status](https://travis-ci.org/shipshapecode/chicaga-tour.svg)](https://travis-ci.org/shipshapecode/chicaga-tour)
[![Code Climate](https://codeclimate.com/github/shipshapecode/chicaga-tour/badges/gpa.svg)](https://codeclimate.com/github/shipshapecode/chicaga-tour)
[![Test Coverage](https://codeclimate.com/github/shipshapecode/chicaga-tour/badges/coverage.svg)](https://codeclimate.com/github/shipshapecode/chicaga-tour/coverage)

This is a Vue wrapper for the [Shepherd](https://github.com/shipshapecode/shepherd), site tour, library.

## Installation

### NPM

```bash
npm install chicaga-tour --save
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
          attachTo: { element: this.$el, on: 'top' },
          text: 'Test step',
        });

        tour.start();
      });
    }
  };
</script>
```


