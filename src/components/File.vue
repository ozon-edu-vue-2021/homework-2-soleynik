<template>
  <div class="file">
    <FileIcon/>{{ this.node.name }}
  </div>
</template>

<script>
import FileIcon from "@/components/Icons/FileIcon";
export default {
  name: "File",
  components:{ FileIcon },
  props: {
    node: {
      type: Object
    }
  }
}
</script>

<style scoped>
.file{
  text-align: left;
  font-size: 18px;
  display: inline-flex;
}
</style>