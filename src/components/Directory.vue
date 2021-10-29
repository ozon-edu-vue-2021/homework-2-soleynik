<template>
  <div class="directory">
    <b>{{ this.name }}</b>
  </div>
</template>

<script>
export default {
  name: "Directory",
  props: {
    type: String,
    name: String,
    contents: Array
  }
}
</script>

<style scoped>

</style>