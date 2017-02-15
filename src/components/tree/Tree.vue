<template>
  <ul class="tree">
    <h1>Contact Tree</h1>
    <tree-item v-for="treeItem in provider" v-bind:item="treeItem"></tree-item>
  </ul>
</template>

<script>
  import TreeItem from './TreeItem'

  export default {
    props: {
      provider: Array
    },

    components: {
      TreeItem
    }
  }
</script>

<style scoped>
  h1 {
    font-family: Times, Serif; 
    font-size:3em;
    font-weight: bold;
  }
</style>