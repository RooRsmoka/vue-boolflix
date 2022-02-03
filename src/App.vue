<template>
  <div id="app">
    <search-bar @search="getMovies"/>
  </div>
</template>

<script>
import axios from 'axios'
import SearchBar from './components/searchBar.vue'
export default {
  name: 'App',
  components: {
    SearchBar
  },
  data() {
    return {
      movies: [],
    }
  },
  methods: {
    getMovies(textInput) {
      axios.get(`https://api.themoviedb.org/3/search/movie?query=${textInput}&api_key=e99307154c6dfb0b4750f6603256716d`).then((response) => {
        this.movies = response.data.results;
      })

    }
  }
}
</script>

<style lang="scss">

</style>
