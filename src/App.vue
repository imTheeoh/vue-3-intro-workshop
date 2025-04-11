<script>
// api url -> https://pokeapi.co/api/v2/pokemon?limit=151
export default {
  data: () => ({
    pokedex: null,
  }),
  methods: {
    async fetchPokemon() {
      const response = await fetch('https://pokeapi.co/api/v2/pokemon?limit=151')
      const pokemonData = await response.json()
      console.log(`${pokemonData.results.length} Pokemon loaded into the Pokédex`)

      this.pokedex = pokemonData.results
    },
  },
  // the created lifecycle hook ensures our api call has already gone and fetched the data before the component gets rendered so the data is immediately visible
  created() {
    this.fetchPokemon()
  },
}
</script>

<template>
  <pre>{{ pokedex }}</pre>
</template>
