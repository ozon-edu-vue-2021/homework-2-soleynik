<template>
  <div id="app">
    <TreeBrowser :node="Items"/>
  </div>
</template>

<script>
import TreeBrowser from './components/TreeBrowser.vue';
import fileData from '/public/static/node_modules.json';
export default {
  name: 'App',
  components: {
    TreeBrowser
  },
  data() {
    return {
      Items: fileData
    }

  }
}
</script>

<style>

</style>
