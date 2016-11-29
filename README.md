# Simple Rating v1.0
Simple Rating component is creating a rating module from font-awesome icons for VueJS. 

For demo you can check [rankvapor](http://en.rankvapor.com)

### Installation

```
$ npm install simple-rating --save
```

### Examples
```vue
<template>
  <form>
    <rating :max="5" :value="3" :disabled="true" :icon="fa fa-user"></rating>
  </form>
  {{ value }}
</template>

<script>
import Rating from 'simple-rating'

export default {
  components: {
    Rating
  }
}
</script>

```

### Badges

![](https://img.shields.io/badge/license-MIT-blue.svg)
![](https://img.shields.io/badge/status-stable-green.svg)

> [kaankilic.com](https://kaankilic.com) &nbsp;&middot;&nbsp;
> GitHub [@kaankilic](https://github.com/kaankilic) &nbsp;&middot;&nbsp;
> Twitter [@kiliclarinkaan](https://twitter.com/kiliclarinkaan)
