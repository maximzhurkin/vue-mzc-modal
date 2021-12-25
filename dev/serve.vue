<script>
import Vue from "vue";
import VueMzcModal from "@/vue-mzc-modal.vue";
import "../src/vue-mzc-modal.css";
import "./serve.css";

export default Vue.extend({
  name: "ServeDev",
  components: {
    VueMzcModal,
  },
  data() {
    return {
      opened: false,
    };
  },
});
</script>

<template>
  <div id="app">
    <button class="demo-button" @click="opened = true">Open</button>
    <vue-mzc-modal v-if="opened" title="Information" @close="opened = false">
      <div class="demo-content">
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sunt
        perferendis sit ratione explicabo fugiat eaque eligendi neque
        consectetur saepe voluptates?
      </div>
    </vue-mzc-modal>
  </div>
</template>
