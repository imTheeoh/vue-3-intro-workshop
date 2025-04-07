<script>
export default {
  data() {
    return {
      movies: [
        {
          name: 'Turbo',
          characters: ['Turbo', 'Chet', 'Guy Gagné'],
        },
        {
          name: 'Need for Speed',
          characters: ['Tobey Marshall', 'Julia Maddon', 'Benny', 'Dino Brewster', 'Finn', 'Anita'],
        },
      ],
      favoriteCharacters: [],
    }
  },
  methods: {
    favoriteCharacter(character) {
      this.favoriteCharacters.push(character)
    },
  },
}
</script>

<template>
  <div>
    <h2>Movies App</h2>
    <p v-if="movies.length === 0">No movies in the system 😓</p>
    <div v-else v-for="movie in movies">
      <h3>{{ movie.name }}</h3>
      <div v-for="character in movie.characters">
        <p>{{ character }}</p>
        <button v-on:click="favoriteCharacter(character)">Favorite Character</button>
      </div>
    </div>

    <h3>Favorited Characters</h3>
    <p v-if="favoriteCharacters.length === 0">No favorite characters in the system 😓</p>
    <ul v-else>
      <li v-for="character in favoriteCharacters">{{ character }}</li>
    </ul>
  </div>
</template>
