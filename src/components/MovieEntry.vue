<script>
export default {
  // props allow us to define what the component is expecting to be passed down from the parent (MoviesList in this case)
  props: {
    // vue will highlight if we pass something down that doesn't match the "prototypes" below. default values can also be set to properties for the event where no props were passed down
    movies: {
      type: Array,
      required: true,
      // default: []
    },
  },
  // new to vue 3 is the ability to document a childs emits in the script. emits define what a child will be sending up, basically a signal conveying that the child wants something to be changed, once changed the data is sent back down
  emits: ['favoriteMovie'],
}

// both props and emits require components to be relatively closely related in order to avoid having to pass data or signals thorugh multiple levels of components
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
      <!-- this button will now when clicked send a signal up to the parent that something needs to change, the parent will capture this signal, do something, and then send the result back down to the child -->
      <button @click="$emit('favoriteMovie', movie.name)">Favorite Movie</button>
    </div>
  </div>
</template>
