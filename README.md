# vue-mzc-modal
Simple Vue2 modal component

![](demo.gif)

[Online demo](https://codesandbox.io/s/competent-heisenberg-g9r0y?file=/src/App.vue)

## Installation
```sh
npm install vue-mzc-modal --save
```

## Usage
```js
import VueMzcModal from "vue-mzc-modal";

export default {
  components: {
    VueMzcModal,
  },
  data() {
    return {
      opened: false,
    };
  },
};
```
```html
<button @click="opened = true">Open</button>
<vue-mzc-modal v-if="opened" title="Info" @close="opened = false">
  content...
</vue-mzc-modal>
```
## Customize
```css
.vue-mzc-modal {
  --vue-mzc-modal-overlay-color: rgba(0,0,0, 0.5);
  --vue-mzc-modal-box-gap: 30px;
  --vue-mzc-modal-box-width: 410px;
  --vue-mzc-modal-box-border-radius: 10px;
  --vue-mzc-modal-box-title-size: 1.25em;
  --vue-mzc-modal-box-text-color: #000000;
  --vue-mzc-modal-box-background-color: #ffffff;
  --vue-mzc-modal-box-close-image: url("data:image/svg+xml...");
}
```