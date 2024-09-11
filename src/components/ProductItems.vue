<template>
  <div class="product-item">
    <h3>{{ product.name }}</h3>
    <p>Price: ₱{{ product.price }}</p>
    <button @click="addToCart">Add to Cart</button>
  </div>
</template>

<script>
export default {
  props: {
    product: Object,
  },
  methods: {
    addToCart() {
      this.$emit('Add-to-cart', this.product);
    },
  },
};
</script>

<style>
.product-item {
  border: 5px solid #00eb5a;
  padding: 10px;
  width: 200px;
  margin-bottom: 10px;
  text-align: center;
}
</style>