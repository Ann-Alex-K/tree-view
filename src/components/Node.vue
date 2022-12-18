<template>
  <div :style="{marginLeft: indent + 'px'}">
    <ul>
     <li>
    <span @click="toggleNode"> {{nodeData.name}} 
     <span v-if="isFolder">[{{ isOpen ? '-' : '+' + nodeData.items.length}}]</span>
    </span>
  
  <Node 
  v-for="item in nodeData.items" 
  :key="item.id" 
  :indent="20" 
  :nodeData="item"
  v-show="isOpen"
/>
     </li>
    <span class="add" v-if="nodeData.items" @click="addItem">Add Item</span>
    </ul>
  </div>
</template>


<script>
export default {
    name: "Node",
    props: {
        nodeData: Object,
        indent: Number
    },
data() {
    return {
      isOpen: false
    }
  },
  computed: {
     isFolder() {
      return  this.nodeData.items && this.nodeData.items.length;
    },
    },
  methods: {
toggleNode() {
   if (this.isFolder) {
        this.isOpen = !this.isOpen;
   }
},
 addItem() {
      this.nodeData.items.push({
        name: 'New node',
        items: [],
      })
 }
  }
}

</script>
