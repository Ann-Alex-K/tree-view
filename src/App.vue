<template>
  <div id="app">
    <h1>My Tree</h1>

    <Node v-for="node in tree" :key="node.id" :nodeData="node" />
  </div>
</template>

<script>
import tree from "./components/tree.json";
import Node from "./components/Node.vue";

export default {
  name: "App",
  components: {
    Node,
  },

  data() {
    return {
      tree: tree,
    };
  },
};
</script>

<style>
h1 {
  font-size: 25px;
  margin: 1rem;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

ul {
  padding: 0.3rem;
  margin: 0;
  box-sizing: border-box;
  width: 100%;
  list-style: none;
}

li > span {
  padding: 0.5rem;
  border: 1px solid #d3d3d3;
  cursor: pointer;
  display: inline-block;
}
li {
  color: #000;
  border-left: 1px solid #d3d3d3;
}
</style>
