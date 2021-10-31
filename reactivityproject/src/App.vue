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
    
    <div class="cart">
      <button class="addToCartButton" v-on:click="addToCart">Add to Cart</button>
      <button class="removeFromCartButton" v-on:click="removeFromCart">Remove From Cart</button>
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
      removeFromCart() {
        if (this.cart > 0) {
        this.cart -= 1;
        }
      },
      updateProduct(lightsaber) {
        this.currentImage = this.lightsaberImages[lightsaber];
      },

    },

  }
</script>

<style>
body {
  font-size: 2rem;
  background-color: black;
  color: aliceblue;
  text-align: center;
}
.product-info {
  font-size: 3rem;
  text-align: center;
  margin-top: 2rem;
  margin-bottom: 2rem;
}

.lightsaber-image {
  width: 50vh;
  border: .1rem solid white;
}

.color-button {
  margin: .5rem;
  font-size: 1rem;
}

.addToCartButton {
  margin: 1rem;
}

.removeFromCartButton {
  margin: 1rem;
}
</style>
