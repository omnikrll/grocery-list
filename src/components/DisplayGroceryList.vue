<template>
    <ul>
        <li v-for="(item, index) in groceries" v-bind:key="index">
            <div class="item-info">{{ item.name }}: ${{ item.price }}, Aisle {{ item.aisle }}</div>
            <button class="delete-btn" @click="deleteItem(index)">✖</button>
        </li>
    </ul>
</template>

<script>

export default {
    name: 'DisplayGroceryList',
    props: ['groceries'],
    emits: ['deleteItem'],
    methods: {
        deleteItem(index) {
            this.$emit('deleteItem', index);
        }
    }
}
</script>

<style scoped>
    ul {
        list-style-type: none;
        margin: 0 auto;
        padding: 0;
        width: 50%;
    }

    li {
        padding: 0.25em;
        border-bottom: 2px groove #999;
        margin-bottom: 0.25em;
        display: flex;
        justify-content: space-between;
    }
</style>