<template>
  <div class="directory">
    {{ this.node.name }}
  </div>
</template>

<script>
export default {
  name: "Directory",
  components:{},
  props: {
    node:{
      type: Object
    }
  }
}
</script>

<style scoped>
.directory{
  text-align: left;
  font-size: 20px;
  display: inline-flex;
}
</style>