# vue-grapesjs-component

[![NPM package](https://img.shields.io/npm/v/vue-grapesjs-component.svg?style=flat-square)](https://www.npmjs.org/package/vue-grapesjs-component)
[![NPM downloads](http://img.shields.io/npm/dm/vue-grapesjs-component.svg?style=flat-square)](https://npmjs.org/package/vue-grapesjs-component)

Use grapesjs like vue component.

## Install
```
npm install --save vue-grapesjs-component
or
yarn add vue-grapesjs-component
```

## Usage

Plugin install:

```js
import Vue from 'vue'
import VueGrapesjsComponent from 'vue-grapesjs-component';

Vue.use(VueGrapesjsComponent)
```
and then:
```html
<vue-grapesjs-component>
  <h1>Hello</h1>
</vue-grapesjs-component>
```

In your layout html add grapesjs library:

```html
<html>
  <head>
    <script src="https://unpkg.com/grapesjs"></script>
    <link rel="stylesheet" href="https://unpkg.com/grapesjs/dist/css/grapes.min.css">
  </head>
</html>
```

## Props

| name   | type   | default | description                                                         |
| ------ | ------ | --------| ------------------------------------------------------------------- |
| config | Object |    -    | Go to grapesjs documentation in initialize section for more details |

## Events

| name   | description                                         | $event                                 |
| ------ | --------------------------------------------------- | -------------------------------------- |
| load   | Fires when editor is initialized                    | editor                                 |
| update | Fires when the structure of the template is updated | `{ components: Array, styles: Array }` |

## Slots

| name    | description      |
| ------- | ---------------- |
| default | Template content |

# License

MIT