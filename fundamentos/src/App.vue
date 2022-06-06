<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <counter title="Entraron" :inicio="10"></counter> -->
  <decicion></decicion>
</template>

<script>
// import Counter from './components/Counter.vue'
import decicion from './components/Decicion.vue'

export default {
  name: 'App',
  components: {
    // Counter
    decicion
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
