<script>
export default {
  // props allow us to define the properties that has to be passed down from a parent component (MoviesList in this case)
  props: {
    // vue will highlight if we pass something down that doesn't match the "prototypes" below. default values can also be set to properties for the event where no props were passed down
    movies: {
      type: Array,
      required: true,
      // default: []
    },
    favoriteMovie: {
      type: Function,
      required: true,
      // default: []
    },
  },
}
</script>

<template>
  <div>
    <p v-if="movies.length === 0">No movies in the system 😓</p>
    <div v-else v-for="movie in movies">
      <h3>{{ movie.name }}</h3>
      <p v-if="movie.characters.length === 0">Unknown cast members 😓</p>
      <ul v-else>
        <li v-for="character in movie.characters">{{ character }}</li>
      </ul>
      <button @click="favoriteMovie(movie.name)">Favorite Movie</button>
    </div>
  </div>
</template>
