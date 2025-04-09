<script>
import MovieEntry from './MovieEntry.vue'

export default {
  components: {
    MovieEntry,
  },
  data() {
    return {
      movies: [
        {
          name: 'Turbo',
          characters: ['Turbo', 'Chet', 'Guy Gagne'],
        },
        {
          name: 'Need for Speed',
          characters: ['Tobey Marshall', 'Finn', 'Pete'],
        },
      ],
      favoriteMovies: [],
    }
  },
  methods: {
    favoriteMovie(movie) {
      this.favoriteMovies.push(movie)
    },
  },
}
</script>

<template>
  <h2>Movies List</h2>
  <div>
    <!-- bind prop & method in this case to data in our parent component. pay attention to when you are passing down to many props because then it might be better to "destructure" the props and only pass down individual properties of a larger object for instance, that larger object can also be refined and massaged with a computed property -->
    <MovieEntry :movies="movies" @favoriteMovie="favoriteMovie" />
  </div>
  <div>
    <h3>Favorited Movies</h3>
    <p v-if="favoriteMovies.length === 0">No favorited movies in the system 😓</p>
    <ul v-else>
      <li v-for="movie in favoriteMovies">{{ movie }}</li>
    </ul>
  </div>
</template>
