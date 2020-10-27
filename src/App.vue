<template>
  <div id="app">
    <Grapes>
      <h1>Hello World</h1>
    </Grapes>
  </div>
</template>

<script>
import Grapes from './components/Grapes';

export default {
  name: 'App',
  components: { Grapes },
}
</script>

<style>
#app {
  height: 100%;
}
</style>
