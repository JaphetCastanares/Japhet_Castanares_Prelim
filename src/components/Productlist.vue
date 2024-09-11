<template>
  <div class="product-list">
    <h2>Product List</h2>
    <div class="product-container">
      <ProductItem 
        v-for="product in products" 
        :key="product.id" 
        :product="product" 
        @add-to-cart="handleAddToCart" 
      />
    </div>

    <div class="cart">
      <h2>Cart:</h2>
      <ul>
        <li v-for="item in cart" :key="item.id">
          {{ item.name }} - ₱{{ item.price }}
        </li>
      </ul>
      <h3>Total: ₱{{ total }}</h3>
    </div>
  </div>
</template>

<script>
import ProductItem from './ProductItems.vue';

export default {
  components: {
    ProductItem,
  },
  data() {
    return {
      products: [
        { id: 1, name: 'Product 1', price: 100 },
        { id: 2, name: 'Product 2', price: 150 },
        { id: 3, name: 'Product 3', price: 300 },
      ],
      cart: [],
    };
  },
  computed: {
    total() {
      return this.cart.reduce((sum, item) => sum + item.price, 0);
    },
  },
  methods: {
    handleAddToCart(product) {
      this.cart.push(product);
    },
  },
};
</script>

<style scoped>
.product-list {
  padding: 10px;
}
.cart {
  margin-top: 20px;
}
</style>