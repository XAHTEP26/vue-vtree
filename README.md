# vue-vtree
Universal and flexible tree component for Vue.js

## Installation

### NPM

```
npm install vue-vtree
```

### CDN
#### jsDelivr
```html
<script src="https://cdn.jsdelivr.net/npm/vue-vtree@latest/dist/v-tree.min.js"></script>
```

#### unpkg
```html
<script src="https://unpkg.com/vue-vtree"></script>
```

## Getting Started
In your script entry point:
```javascript
import Vue from 'vue';
import VTree from 'vue-vtree';
Vue.component('v-tree', VTree);
```

## Usage

Just write one level of tree in scoped-slot and pass children data to empty child v-tree component and it will inherit the parent slot template.

```vue
<template>
  <div id="app">
    <v-tree :scope-data="menu">
      <ul slot-scope="menuLevel">
        <li v-for="menuItem in menuLevel">
          <a :href="menuItem.url">{{ menuItem.title }}</a>
          <v-tree v-if="menuItem.children" :scope-data="menuItem.children"></v-tree>
        </li>
      </ul>
    </v-tree>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        menu: [
          { title: 'Home', url: '#' },
          {
            title: 'Posts',
            url: '#',
            children: [
              { title: 'Development', url: '#' },
              { title: 'Design', url: '#' },
              { title: 'Other', url: '#' }
            ]
          },
          {
            title: 'Handbooks',
            url: '#',
            children: [
              {
                title: 'HTML',
                url: '#',
                children: [
                  { title: 'a', url: '#' },
                  { title: 'span', url: '#' },
                  { title: 'div', url: '#' }
                ]
              },
              {
                title: 'CSS',
                url: '#',
                children: [
                  { title: 'display', url: '#' },
                  { title: 'position', url: '#' },
                  { title: 'background', url: '#' },
                  { title: 'border', url: '#' }
                ]
              },
            ]
          },
        ]
      }
    }
  }
</script>
```
[Live Demo](https://codepen.io/XAHTEP26/pen/mQRyRB)

Property "scope-data" can take any value.

[Demo for JSON](https://codepen.io/XAHTEP26/pen/zMNONz)

[Demo for Number](https://codepen.io/XAHTEP26/pen/PxWwaa)

## License
[The MIT License](LICENSE)
