<template>
    <div class="item-list">
      <h2>Product List</h2>
      <Item
        v-for="(product, index) in filteredItems" :key="index" :item="product" @add-to-cart="handleAddToCart"/>
    </div>
  </template>
  
  <script>
  import Item from './Item.vue';
  
  export default {
    name: 'ItemList',
    components: {
      Item,
    },
    props: {
      products: {
        type: Array,
        required: true,
      },
    },
    computed: {
      filteredItems() {
        return this.products.filter((product) => product.visible);
      },
    },
    methods: {
      handleAddToCart(item) {
        console.log(`1 x ${item.name} - $${item.price}`);
      },
    },
  };
  </script>
  
  <style scoped>
  .item-list {
    padding: 20px;
    margin: 20px;
    text-align: center;
  }
  </style>
  