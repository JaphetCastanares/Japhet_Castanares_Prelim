<template>
    <div v-if="isVisible" class="item">
      <h3>{{ item.name }}</h3>
      <p>Price: ${{ item.price.toFixed(2) }}</p>
      <button @click="addToCart">Add to Cart</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Item',
    props: {
      item: {
        type: Object,
        required: true,
      },
    },
    computed: {
      isVisible() {
        return this.item.visible;
      },
    },
    methods: {
      addToCart() {
        console.log(`Added to cart: ${this.item.name} - $${this.item.price}`);
        this.$emit('add-to-cart', this.item);
      },
    },
  };
  </script>
  
  <style scoped>
  .item {
    border: 1px solid #ccc;
    padding: 10px;
    margin-bottom: 10px;
    border-radius: 5px;
  }
  button {
    background-color: #28a745;
    color: white;
    border: none;
    padding: 5px 10px;
    cursor: pointer;
    border-radius: 3px;
  }
  </style>