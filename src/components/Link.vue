<template>
  <div class="link">
    <LinkIcon/>{{ this.node.name }}
  </div>
</template>

<script>
import LinkIcon from "@/components/Icons/LinkIcon";
export default {
  name: "Link",
  components:{ LinkIcon },
  props: {
    node:{
      type: Object
    }
  }
}
</script>

<style scoped>
.link{
  text-align: left;
  font-size: 18px;
  font-style: italic;
  display: inline-flex;
}

</style>