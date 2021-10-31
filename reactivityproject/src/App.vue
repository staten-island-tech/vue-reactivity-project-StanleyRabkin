<template>
  <div id="app">
    <div class="product-info">
      <hi class="header">{{ product }}</hi>
    </div>
    <div class="product-image">
      <img class="lightsaber-image" v-bind:src="currentImage" />
    </div>
    <button
      class="color-button"
      v-for="lightsaberColor in lightsaberColors"
      :key="lightsaberColor"
       @click="updateProduct(lightsaberColor)">
        {{ lightsaberColor }}
      
    </button>
    <button v-on:click="addToCart">Add to Cart</button>
    <div class="cart">
      <p>Cart({{ cart }})</p>
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
        lightsaberColors: ['Blue', 'Red', 'White', 'Cyan', 'Green'],
        currentImage: require("./assets/blue-lightsaber.jpg"),
        lightsaberImages: {
          Blue: require("./assets/blue-lightsaber.jpg"),
          Red: require("./assets/red-lightsaber.jpg"),
          White: require("./assets/white-lightsaber.jpg"),
          Cyan: require("./assets/cyan-lightsaber.jpg"),
          Green: require("./assets/green-lightsaber.jpg"),
        },
        cart: 0,
       }
    },
    methods: {
      addToCart() {
        this.cart += 1;
      },
      updateProduct(lightsaber) {
        this.currentImage = this.lightsaberImages[lightsaber];
      },

    },

  }
</script>

<style>
#app {
  font-size: 2rem;
  background-color: black;
  color: aliceblue;
}
.header {
  font-size: 3rem;
  text-align: center;
}
.lightsaber-image {
  width: 60vh;
}
</style>
