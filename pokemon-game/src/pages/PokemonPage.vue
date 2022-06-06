<template>
  <div>
    <div v-if="!pokemon">
      <h1>Buscando Pokemon</h1>
    </div>
    <div v-else>
      <h1>Quien es este Pokemon?</h1>
      <PokemonPickture :pokemonId="pokemon.id" :showPokemon="showPokemon">
      </PokemonPickture>
      <PokemonOption :pokemons="pokemonArr" @selection="checkPokemon($event)"></PokemonOption>
    </div>
    <button>Juega de nuevo</button>
  </div>
</template>

<script>
import PokemonOption from "@/components/PokemonOption.vue";
import PokemonPickture from "@/components/PokemonPickture.vue";
import getPokemonOptions from "@/helpers/getPokemonOptions.js";

export default {
  components: {
    PokemonOption,
    PokemonPickture,
  },
  data() {
    return {
      pokemonArr: [],
      pokemon: null,
      showPokemon: false,
    };
  },
  methods: {
    async mixPokemonArr() {
      this.pokemonArr = await getPokemonOptions();
      const rndInt = Math.floor(Math.random() * 4);
      this.pokemon = this.pokemonArr[rndInt];
    },
    checkPokemon(pokemonId){
        if(pokemonId === this.pokemon.id){
            this.showPokemon = true;
        }
    }
  },
  mounted() {
    this.mixPokemonArr();
  },
};
</script>
