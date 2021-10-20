<template>
  <div id="app">
    <hi>{{ product }}</hi>
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
    }
  }
}
</script>

<style>
#app {
  font-size: 1rem;
}
</style> 