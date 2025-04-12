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
    return {
      currentPage: null,
    }
  },
  // use computed when you want to obtain a value based on other reactive data. results are cached and recalculated only when necessary. computed manages data
  computed: {},
  // use watch when you want to watch a specific value and perform side effects. good for reacting to state changes without returning a value. watch manages actions that should happen based on state
  watch: {},
  // methods are simply methods that operate on reactive data properties
  methods: {
    setPageRandomCounter() {
      this.currentPage = 'RandomCounter'
    },
    setPageLoopingUsers() {
      this.currentPage = 'LoopingUsers'
    },
    setPageMoviesList() {
      this.currentPage = 'MoviesList'
    },
    setPageFormCapture() {
      this.currentPage = 'FormCapture'
    },
  },
}
</script>

<!-- <template> manages html -->
<template>
  <nav>
    <a href="#" @click.prevent="setPageRandomCounter">Random Counter</a>
    <a href="#" @click.prevent="setPageLoopingUsers">Looping Users</a>
    <a href="#" @click.prevent="setPageMoviesList">Movies List</a>
    <a href="#" @click.prevent="setPageFormCapture">Form Capture</a>
  </nav>
  <RandomCounter v-if="currentPage === 'RandomCounter'" />
  <LoopingUsers v-else-if="currentPage === 'LoopingUsers'" />
  <MoviesList v-else-if="currentPage === 'MoviesList'" />
  <FormCapture v-else-if="currentPage === 'FormCapture'" />
</template>

<!-- <style> manages css -->
<style></style>
