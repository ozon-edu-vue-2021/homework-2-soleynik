<template>
  <div class="link">
    <LinkIcon/>{{ this.name }}
  </div>
</template>

<script>
import LinkIcon from "@/components/Icons/LinkIcon";
export default {
  name: "Link",
  components:{ LinkIcon },
  props: {
    type:{
      type: String
    },
    name: {
      type: String
    },
    target: {
      type: String
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