<template>
  <div id="app">
    <div class="product-info">
      <hi>{{ product }}</hi>
    </div>
    <div class="product-image">
      <img v-bind:src="img"/>
    </div>
    
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data() { 
    return{
       product: 'Lightsaber',
       selectedVariant: 1,
       img: require("./assets/blue-lightsaber.jpg"),
       variants: {
         {
         variantID:1,
         variantColor: "blue",
         variantImage: require("./assets/blue-lightsaber.jpg"),
         }
       }
       
    }
  }
}
</script>

<style>
#app {
  font-size: 1rem;
}
</style> 