<template>
  <div id="app">
    <ItemList :products="products" />
  </div>
</template>

<script>
import ItemList from './components/Itemlist.vue';

export default {
  name: 'App',
  components: {
    ItemList,
  },
  data() {
    return {
      products: [
        { name: 'Efren Jacob', price: 100, visible: true },
        { name: 'Jarred Ruba', price: 200, visible: true },
        { name: 'Louie Bioncog', price: 300, visible: true }, 
        { name: 'Ivan Clint Yuichi', price: 400, visible: true },
        { name: 'Paul Jacob Tocmo', price: 500, visible: true },
      ],
    };
  },
};
</script>

<style>
#app {
  margin: auto;
}
</style>
