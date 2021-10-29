<template>
  <div>
    <i>{{ this.name }}</i>
  </div>
</template>

<script>
export default {
  name: "Link",
  props: {
    type: String,
    name: String,
    target: String
  }
}
</script>

<style scoped>

</style>