<template>
  <div id="app">
    <hi>{{ product }}</hi>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
  },
  data() { 
    return{
       product: 'lightsaber',
    }
  }
}
</script>

<style>
#app {
  font-size: 1rem;
}
</style>