<template>
  <div id="app">
    <div>
      <button @click="handleMessageShowing">Show Message</button>
    </div>
    <vue-grapesjs-component class="editor">
      <h1>Hello World</h1>
      <p v-show="showingMessage">Hello everyone</p>
    </vue-grapesjs-component>
  </div>
</template>

<script>
import Vue from 'vue';
import VueGrapesjsComponent from '@/vue-grapesjs-component.vue';

export default Vue.extend({
  name: 'ServeDev',
  components: {
    VueGrapesjsComponent
  },
  data() {
    return {
      showingMessage: false
    }
  },
  methods: {
    handleMessageShowing() {
      this.showingMessage = !this.showingMessage
    }
  }
});
</script>

<style>
#app {
  display: flex;
  height: 100%;
  flex-direction: column;
}
.editor {
  flex:1;
}
</style>