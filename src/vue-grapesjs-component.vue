<template>
  <div class="wrapper">
    <div id="gjs" />
    <div ref="children" class="hidden">
      <slot />
    </div>
  </div>
</template>

<script>
import "grapesjs/dist/css/grapes.min.css";
import grapesjs from "grapesjs";

export default {
  name: 'VueGrapesjsComponent', // vue component name
  props: {
    config: {
      type: Object
    }
  },
  data() {
    return {
      editor: {}
    }
  },
  mounted() {
    const configDefault = {
      container: '#gjs',
      components: this.$refs.children.innerHTML,
      height: '100%',
      width: 'auto',
    }
    this.editor = grapesjs.init({
      ...configDefault,
      ...this.config
    });
    this.editor.on('load', (editor) => {
      this.$emit('load', editor)
    });
    this.editor.on('update', () => {
      this.$emit('update', {
        components: JSON.parse(JSON.stringify(this.editor.getComponents())),
        styles: JSON.parse(JSON.stringify(this.editor.getStyle()))
      });
    });
  },
  updated() {
    this.$nextTick(() => {
      this.editor.setComponents(this.$refs.children.innerHTML)
    })
  }
}
</script>

<style scoped>
  .wrapper {
    display: flex;
    flex-direction: column;
    height: 100%;
  }
  .hidden {
    display: none;
  }
</style>
