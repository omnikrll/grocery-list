<template>
  <AddGroceryItem @add-new-item="addNewItem"/>
  <DisplayGroceryList @delete-item="deleteItem" v-model:groceries="groceries"/>
</template>

<script>
import AddGroceryItem from './components/AddGroceryItem.vue'
import DisplayGroceryList from './components/DisplayGroceryList.vue'

export default {
  name: 'App',
  data () {
    return {
      groceries: []
    }
  },
  components: {
    AddGroceryItem,
    DisplayGroceryList
  },
  methods: {
    addNewItem(item) {
      this.groceries.push(item);
    },
    deleteItem(index) {
      this.groceries.splice(index, 1);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
