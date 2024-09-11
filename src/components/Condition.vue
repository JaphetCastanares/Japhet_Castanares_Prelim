<template>
  <div>
    <h3>Detecting if user is Gay.....</h3>
    <p v-if="user.isGay">It has been detected that you are Gay</p>
    <p v-if="user.isGay">Stay away from me {{ user.name }}</p>
    <p v-else>Supp {{ user.name }}</p>
  </div>
</template>
<script>
  export default{
    data (){
      return {
        user : {
          isGay: true,
          name: 'Bro Bro'
        }
      };
    }
  };
</script>
<style>
  h3 {
    font-weight: bold;
  }
</style>