<template>
  <div>
    <ul>
    <li v-for="(butang, index) in butangs" :key="index">
      {{ butang.name }} - ${{ butang.price }} - {{ butang.desc }}
    </li>
  </ul>
  </div>
</template>

<script>
  export default {
    data (){
      return {
        butangs : [
          {name: "Jamal", price: 30,desc: "Is experienced in picking cotton."},
          {name: "Amani", price: 50,desc: "Big muscles and loyal slave"},
          {name: "Caleb", price: 20,desc: "is very annoying and rebellios"},
        ]
      };
    }
  };
</script>

<style scoped>

</style>
