<template>
  <div id="app">
    <head-bar @search="getContent"/>
    <main-box :movies="movies"/>
  </div>
</template>

<script>
import axios from 'axios'
import HeadBar from './components/HeadBar.vue'
import MainBox from './components/MainBox.vue'

export default {
  name: 'App',
  components: {
    HeadBar,
    MainBox
  },
  data() {
    return {
      movies: [],
    }
  },
  methods: {
    getContent(textInput) {
      axios.get(`https://api.themoviedb.org/3/search/movie?query=${textInput}&api_key=e99307154c6dfb0b4750f6603256716d`).then((response) => {
        this.movies = response.data.results;
      });
    }
  }
}
</script>

<style lang="scss">
@import './style/common.scss';
</style>
