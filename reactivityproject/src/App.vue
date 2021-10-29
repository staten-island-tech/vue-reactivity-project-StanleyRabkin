<template>
  <div id="app">
    <div class="product-info">
      <hi>{{ product }}</hi>
    </div>
    <div class="product-image">
      <img class="lightsaber-img" v-bind:src="img"/>
    </div>
    <button class="color-button" v-for="variant in variants" :key="variant.variantID">
      <p @click="updateProduct(variant.variantImage)">{{ variant.variantColor }}</p>
    </button>
    <button v-on:click="addToCart">Add to Cart</button>
    <div class="cart">
      <p>Cart({{cart}})</p>
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
      //  selectedVariant: 0,
        // currantImage: require("./assets/blue-lightsaber.jpg"),
        currentImage: '',
        lightsaberImages: {
          
        }
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
        ],
        cart: 0
       }
    },
    methods: {
      addToCart() {
        this.cart += 1;
      },
      updateProduct(currentImage) {
        this.currentImage = this.variantImage
      }

    },
    
  }
</script>

<style>
#app {
  font-size: 1rem;
  background-color: black;
  color: aliceblue;
}
.lightsaber-img{
  width: 30rem;
}
</style>   