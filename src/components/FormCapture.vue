<script>
export default {
  data() {
    return {
      clients: [],
      newClient: {
        name: '',
        surname: '',
      },
    }
  },
  methods: {
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

<template>
  <h2>Form Capture</h2>
  <pre>{{ newClient }}</pre>
  <form action="">
    <div>
      <label for="client__name">Client Name:</label>
      <input type="text" name="client__name" id="client__name" v-model="newClient.name" />
    </div>
    <div>
      <label for="client__surname">Client Surname:</label>
      <input type="text" name="client__surname" id="client__surname" v-model="newClient.surname" />
    </div>
    <button type="submit" v-on:click.prevent="addClient">Add Client</button>
  </form>
  <div>
    <h3>Clients</h3>
    <p v-if="clients.length === 0">No clients in the system 😓</p>
    <ul v-else>
      <li v-for="client in clients">{{ client.name }} {{ client.surname }}</li>
    </ul>
  </div>
</template>
