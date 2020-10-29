<template>
  <div id="app">
    <div>
      <button @click="handleMessageShowing">Show Message</button>
    </div>
    <Grapes class="editor">
      <h1>Hello World</h1>
      <p v-show="showingMessage">Hello everyone</p>
    </Grapes>
  </div>
</template>

<script>
import Grapes from './components/Grapes';

export default {
  name: 'App',
  components: { Grapes },
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
}
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
