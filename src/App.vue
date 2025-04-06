<!-- <script> manages js -->
<script>
export default {
  // reactive data properties
  data() {
    return {
      message: 'Yes it works!',
      numbers: [1, 2, 3, 4, 5],

      count: 0,
      countIncrementAmount: 1,

      users: [
        {
          name: 'Theo',
          surname: 'Snyman',
        },
        {
          name: 'Kaitlyn',
          surname: 'Bezuidenhout',
        },
        {
          name: 'Thomas',
          surname: 'Shelby',
        },
      ],

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

      clients: [],
      newClient: {
        name: '',
        surname: '',
      },
    }
  },
  // use computed when you want to obtain a value based on other reactive data. results are cached and recalculated only when necessary. computed manages data
  computed: {
    changeCountDescriptionParagraph() {
      if (this.count < 10) {
        return 'A teenie count of'
      } else if (this.count < 50) {
        return 'A sizable count of'
      } else if (this.count < 100) {
        return 'A relatively large count of'
      } else {
        return 'A hugeeee count of'
      }
    },
  },
  // use watch when you want to watch a specific value and perform side effects. good for reacting to state changes without returning a value. watch manages actions that should happen based on state
  watch: {},
  // methods are simply methods that operate on reactive data properties
  methods: {
    incrementCount(event) {
      this.count += this.countIncrementAmount
    },

    favoriteCharacter(character) {
      this.favoriteCharacters.push(character)
    },

    addClient(event) {
      this.clients.push(this.newClient)
      this.newClient = {
        name: '',
        surname: '',
      }
    },
  },
}
</script>

<!-- <template> manages html -->
<template>
  <div>
    <h1>{{ message }}</h1>
    <ul>
      <li v-for="number in numbers">{{ number }}</li>
    </ul>
  </div>

  <div>
    <h2>Simple Count Button</h2>
    <input
      type="number"
      name="count__increment-val"
      id="count__increment-val"
      v-model="countIncrementAmount"
    />
    <button v-on:click="incrementCount">Increment Count</button>
    <p>{{ changeCountDescriptionParagraph }} {{ count }}</p>
  </div>
  <hr />
  <div>
    <h2>User Looping</h2>
    <p v-if="users.length === 0">No users in the system 😓</p>
    <p v-else v-for="(user, index) in users">
      User number {{ index }} is {{ user.name }} {{ user.surname }}.
    </p>
  </div>
  <hr />
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
  <hr />
  <div>
    <h2>Form Capture</h2>
    <pre>{{ newClient }}</pre>
    <form action="">
      <div>
        <label for="client__name">Client Name:</label>
        <input type="text" name="client__name" id="client__name" v-model="newClient.name" />
      </div>
      <div>
        <label for="client__surname">Client Surname:</label>
        <input
          type="text"
          name="client__surname"
          id="client__surname"
          v-model="newClient.surname"
        />
      </div>
      <button type="submit" v-on:click.prevent="addClient">Add Client</button>
    </form>
    <h3>Clients</h3>
    <p v-if="clients.length === 0">No clients in the system 😓</p>
    <ul v-else>
      <li v-for="client in clients">{{ client.name }} {{ client.surname }}</li>
    </ul>
  </div>
</template>

<!-- <style> manages css -->
<style></style>
