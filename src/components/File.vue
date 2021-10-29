<template>
  <div class="file">
    {{ this.name }}
  </div>
</template>

<script>
export default {
  name: "File",
  props: {
    type: String,
    name: String
  }
}
</script>

<style scoped>

</style>