<template>
  <Pokemonpage></Pokemonpage>

</template>

<script>
import Pokemonpage from './pages/PokemonPage.vue'

export default {
  name: 'App',
  components: {
    Pokemonpage,
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
