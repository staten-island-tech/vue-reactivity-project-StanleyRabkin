<template>
  <div id="app">
    <div class="product-info">
      <hi>{{ product }}</hi>
    </div>
    <div class="product-image">
      <img v-bind:src="img"/>
    </div>
    <div v-for="variant in varients" :key="variant.variantID">
      <p>{{ variant.variantColor }}</p>
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
       selectedVariant: 0,
       img: require("./assets/blue-lightsaber.jpg"),
       variants: [
         {
         variantID:1,
         variantColor: "blue",
         variantImage: require("./assets/blue-lightsaber.jpg"),
         },
          {
         variantID:2,
         variantColor: "red",
         variantImage: require("./assets/red-lightsaber.jpg"),
         },
          {
         variantID:3,
         variantColor: "green",
         variantImage: require("./assets/green-lightsaber.jpg"),
         },
          {
         variantID:4,
         variantColor: "white",
         variantImage: require("./assets/white-lightsaber.jpg"),
         },
         {
          variantID:5,
         variantColor: "cyan",
         variantImage: require("./assets/cyan-lightsaber.jpg"),
         },
        ]
       }
       
    },
    methods: {
      updateProduct: function (variantImage) {
        this.image = variantImage
      }

    }
  }
</script>

<style>
#app {
  font-size: 1rem;
}
</style>   