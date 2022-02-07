<template>
  <div id="app">
    <head-bar @search="searchContent"/>
    <popular-box v-if="!flag" :popularMovies="popularMovies" :popularSeries="popularSeries"/>
    <main-box :searchedMovies="searchedMovies" :searchedSeries="searchedSeries"/>
  </div>
</template>

<script>
import axios from 'axios'
import HeadBar from './components/HeadBar.vue'
import PopularBox from './components/PopularBox.vue'
import MainBox from './components/MainBox.vue'


export default {
  name: 'App',
  components: {
    HeadBar,
    PopularBox,
    MainBox
  },
  data() {
    return {
      api_key: 'e99307154c6dfb0b4750f6603256716d',
      popularMovies: [],
      popularSeries: [],
      searchedMovies: [],
      searchedSeries: [],
      flag: false,
    }
  },
  mounted() {
    axios.get(`https://api.themoviedb.org/3/movie/popular?api_key=${this.api_key}&page=1`)
      .then((response) => {
        this.popularMovies = response.data.results;
      });
    axios.get(`https://api.themoviedb.org/3/tv/popular?api_key=${this.api_key}&page=1`)
      .then((response) => {
        this.popularSeries = response.data.results;
      });
  },
  methods: {
    searchContent(textInput) {
      this.getMovies(textInput);
      this.getSeriesTv(textInput);
      this.flag = true;
    },
    async getMovies(textInput) {
      this.searchedMovies = await this.apiCall('movie', textInput)
    },

    async getSeriesTv(textInput) {
      this.searchedSeries = await this.apiCall('tv', textInput)
    },

    async apiCall(type, textInput) {

      const params = {
        query: textInput,
        api_key: this.api_key
      }
      const results = await axios.get(`https://api.themoviedb.org/3/search/${type}`, { params }
        )
        .then((response) => {
          return response.data.results;
        })
      return results
    }
  }
}
</script>

<style lang="scss">
@import './style/common.scss';
</style>
