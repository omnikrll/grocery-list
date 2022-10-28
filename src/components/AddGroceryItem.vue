<template>
  <div>
    <input type="text" placeholder="Name" v-model="item.name"/>
    <input type="number" min="0.00" placeholder="Price" v-model="item.price"/>
    <input type="number" min="0" placeholder="Aisle" v-model="item.aisle"/>
    <button @click="handleNewItem">Add Item</button>
  </div>
</template>

<script>
export default {
  name: 'AddGroceryItem',
  data () {
    return {
      item: {
        name: '',
        price: '',
        aisle: ''
      }
    }
  },
  emits: ['addNewItem'],
  methods: {
    handleNewItem() {
      this.$emit('addNewItem', this.item);
      this.item = {
        name: '',
        price: '',
        aisle: ''
      };
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
  text-align: center;
}

input, button {
  display: block;
  margin: 0.25em auto;
}
</style>
