<template>
  <div id="app">
    <tree v-bind:provider="treeProvider"></tree>
  </div>
</template>

<script>
  import Tree from './components/tree/Tree'

  const treeProvider = [
      {
          id:1,
          name: "Friends",
          type: "Group",
          contacts: [
              {id:2, name: "Udi", type: "Contact"},
              {id:3, name: "Tommy", type: "Contact"},
              {
                  id:6,
                  name: "Old Friends",
                  type: "Group",
                  contacts: [
                      {id:7, name: "Itay", type: "Contact"},
                  ]
              },
          ]
      },
      {
          id:4,
          name: "Family",
          type: "Group",
          contacts: [
              {id:5, name: "Roni", type: "Contact"},
          ]
      },
      {id: 8, name: "Ori", type: "Contact"},
  ];

  export default {
    name: 'app',

    data() {
      return {
        treeProvider: treeProvider
      }
    },

    components: {
      Tree
    }
  }
</script>

<style>
#app {
  font-family: Times, Serif;
  color: #2c3e50;
  margin-top: 60px;
}
</style>