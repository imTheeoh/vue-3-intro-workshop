<script>
export default {
  data() {
    return {
      count: 0,
      countIncrementAmount: 1,
    }
  },
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
  methods: {
    incrementCount(event) {
      this.count += this.countIncrementAmount
    },
  },
}
</script>

<template>
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
</template>
