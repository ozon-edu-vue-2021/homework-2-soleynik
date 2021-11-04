<template>
  <div class="view">

    <div
      v-if="isDirectory"
      @click="toggle"
      :node="node"
      :style="{'margin-left': `${depth * 20}px`}"
    >
      <span v-if="isToggled">
        <DirectoryOpenedIcon/>
      </span>
      <span v-else>
        <DirectoryClosedIcon/>
      </span>
      {{ this.node.name }}
    </div>
    <File v-else-if="isFile"
          :type="node.type"
          :name="node.name"
          :style="{'margin-left': `${depth * 20}px`}"
    >
    </File>
    <Link v-else-if="isLink"
          :type="node.type"
          :name="node.name"
          :target="node.target"
          :style="{'margin-left': `${depth * 20}px`}"
    >
    </Link>
  <div v-if="isToggled" class="tree_browser_wrapper">
    <TreeBrowser
        v-for="(content,index) in node.contents"
        :key="index"
        :node="content"
        :depth="depth + 1"
    />
  </div>
  </div>


</template>
<script>
import File from "@/components/File.vue";
import Link from "@/components/Link.vue";
import DirectoryClosedIcon from "@/components/Icons/DirectoryClosedIcon";
import DirectoryOpenedIcon from "@/components/Icons/DirectoryOpenedIcon";

export default {
  name: "TreeBrowser",
  components: {
    File,
    Link,
    DirectoryClosedIcon,
    DirectoryOpenedIcon
  },
  props: {
    node: Object,
    depth: {
      type: Number,
      default: 0
    }
  },
  data(){
    return{
      isToggled: false,
    }
  },
  methods: {
    toggle: function(){
      if(this.isDirectory){
        this.isToggled = !this.isToggled
      }
    }
  },
  computed:{
    isDirectory: function (){
      return this.node.contents && this.node.contents.length;
    },
    isFile: function (){
      return this.node.type === 'file';
    },
    isLink: function (){
      return this.node.type === 'link';
    },
  }

}
</script>

<style scoped>

</style>