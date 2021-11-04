<template>
  <div class="directory">
    <DirectoryClosedIcon/>{{ this.name }}
  </div>
</template>

<script>
import DirectoryClosedIcon from "@/components/Icons/DirectoryClosedIcon";
export default {
  name: "Directory",
  components:{DirectoryClosedIcon},
  props: {
    type:{
      type: String
    },
    name:{
      type: String
    },
    contents:{
      type: Array
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