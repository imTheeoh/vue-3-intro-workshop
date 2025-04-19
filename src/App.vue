<template>
  <h1>{{ helloWorld }}</h1>
  <p>My name is {{ myName }}.</p>
</template>

<script>
export default {
  setup() {
    // The setup lifecycle is the earliest point in the lifecycle of a component, ideal for asynchronous operations where data has to be fetched etc...

    // The composition api is basically vanilla javascript because composition api gives us freedom and flexibility. Options api provides more consistency but lack freedom and flexibility

    const helloWorld = 'Hello World!'
    const myName = 'Theo'

    return {
      // Everything we want to expose has to be returned manually in composition api
      helloWorld,
      myName,
    }

    // ASYNC OPERATIONS SHOULD NOT BE RUN IN SETUP INSIDE THE APP.VUE SINCE THE ROOT COMPONENT NEEDS TO BE IN A CONSTANTLY STABLE STATE. COMPONENTS CAN BE HELD ONTO A BIT AND GIVEN FALLBACKS IF THEIR ASYNC OPERATIONS FAIL BUT THE ROOT COMPONENT DOES NOT HAVE THE SAME LUXURIES
  },
}
</script>

<style></style>
