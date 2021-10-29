<template>
  <div class="view">
    <div
      @click="isToggled = !isToggled"
      :style="{'margin-left': `${depth * 20}px`}"
      class="node"
    >
      <span
          class="type">
        {{ isToggled ? "-" : "+"}}
      </span>
      {{ node.name }}
    </div>

    <TreeBrowser
        v-for="content in node.contents"
        :key="content.name"
        :node="content"
        :depth="depth + 1"
    />
  </div>



<!--    <Directory-->
<!--      v-if="isDirectory"-->
<!--    >-->
<!--    </Directory>-->
<!--    <File-->
<!--      v-else-if="isFile"-->
<!--    >-->
<!--      </File>-->
<!--    <Link-->
<!--      v-else-if="isLink"-->
<!--    >-->
<!--    </Link>-->


</template>
<script>

// import File from "@/components/File";
// import Directory from "@/components/Directory";
// import Link from "@/components/Link";

export default {
  name: "TreeBrowser",
  // components: {Link, Directory, File},
  props: {
    node: Object,
    depth: {
      type: Number,
      default: 0
    }
  },
  data(){
    return{
      isToggled: false
    }
  },
  methods:{
    nodeType(node){
      if(node.contents){
        return "directory"
      }else if(node.type === 'file'){
        return "file"
      }else if(node.type === 'link'){
        return "link"
      }
    }
  },
  computed:{
    isDirectory: function (){
      return this.node.contents;
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
.node{
  text-align: left;
  font-size: 18px;
}
</style>