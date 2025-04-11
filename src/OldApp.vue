<!-- <script> manages js -->
<script>
import RandomCounter from './components/RandomCounter.vue'
import LoopingUsers from './components/LoopingUsers.vue'
import MoviesList from './components/MoviesList.vue'
import FormCapture from './components/FormCapture.vue'
import BaseLayout from './components/BaseLayout.vue'

export default {
  // components option allows us to register components that we want to use throughout our app or within other components
  components: {
    RandomCounter,
    LoopingUsers,
    MoviesList,
    FormCapture,
    BaseLayout,
  },
  // reactive data properties
  data() {
    return {}
  },
  // use computed when you want to obtain a value based on other reactive data. results are cached and recalculated only when necessary. computed manages data
  computed: {},
  // use watch when you want to watch a specific value and perform side effects. good for reacting to state changes without returning a value. watch manages actions that should happen based on state
  watch: {},
  // methods are simply methods that operate on reactive data properties
  methods: {},
}
</script>

<!-- <template> manages html -->
<template>
  <BaseLayout>
    <template v-slot:section-1>
      <RandomCounter />
    </template>
    <template v-slot:section-2>
      <LoopingUsers />
    </template>
    <template v-slot:section-3>
      <MoviesList />
    </template>
    <template v-slot:footer>
      <FormCapture />
    </template>
  </BaseLayout>
</template>

<!-- <style> manages css -->
<style></style>
