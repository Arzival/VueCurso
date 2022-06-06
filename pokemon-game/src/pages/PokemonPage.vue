<template>
    <div>
        <h1>Quien es este Pokemon?</h1>
        <PokemonPickture :pokemonId="649" :showPokemon="true"></PokemonPickture>
        <PokemonOption :pokemons="pokemonArr"></PokemonOption>

    </div>
</template>

<script>
import PokemonOption from '@/components/PokemonOption.vue'
import PokemonPickture from '@/components/PokemonPickture.vue'
import getPokemonOptions from '@/helpers/getPokemonOptions.js'

export default {
    components: {
        PokemonOption,
        PokemonPickture
    },
    data() {
        return {
            pokemonArr: []
        }
    },
    methods: {
        async mixPokemonArr() {
            this.pokemonArr = await getPokemonOptions()
            
        }
    },
    mounted() {
        this.mixPokemonArr()
    }
}
</script>
