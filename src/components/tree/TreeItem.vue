<template>
  <li class="tree-item">
    <div v-on:click="toggleItem">
      {{ item.name }}  
    </div>
    <ul v-if="isFolder" v-show="isOpen">
      <tree-item v-for="contact in item.contacts" v-bind:item="contact"></tree-item>
    </ul>
  </li>
</template>

<script>
  export default {
    name: 'tree-item',

    props: {
      item: Object,
      required: true
    },

    data: function () {
      return {
        isOpen: false
      }
    },

    computed: {
      isFolder: function () {
        // return this.item.children && this.item.children.length > 0
        return this.item.type === "Group" && this.item.contacts && this.item.contacts.length > 0    
      }
    },
    
    methods: {
      toggleItem: function () {
        if (this.isFolder) {
          this.isOpen = !this.isOpen
        }
      }
    }
  }
</script>

<style>
  .tree-item {
    font-family: Times, Serif; 
    padding: 5px;
    font-size:25px;
    list-style: none;
  }

  .tree-item div:hover {
    cursor: pointer;
  }
</style>