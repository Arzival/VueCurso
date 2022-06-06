<template>
    <div class="pokemon-container">
        <img class="hidden-pokemon" :src="this.imgSrc" alt="">

        <img v-if="this.showPokemon" class="fade-in" :src="this.imgSrc" alt="pokemon">
    </div>

</template>

<script>
export default {
    props: {
        pokemonId: {
            type: Number,
            required: true
        },
        showPokemon: {
            type: Boolean,
            required: true,
            default: false
        }
    },
    computed: {
        imgSrc() {
            return `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/${this.pokemonId}.svg`
        }
    }
}
</script>

<style>
</style>