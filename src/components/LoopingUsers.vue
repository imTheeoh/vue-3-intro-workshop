<script>
export default {
  data() {
    return {
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
    }
  },
}
</script>

<template>
  <h2>User Looping</h2>
  <p v-if="users.length === 0">No users in the system 😓</p>
  <p v-else v-for="(user, index) in users">
    User number {{ index }} is {{ user.name }} {{ user.surname }}.
  </p>
</template>
