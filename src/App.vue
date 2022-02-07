<template>
  <div id="app">
    <header-container @search="searchInput" />
    <main-container
      :movieList="filteredMovies"
      :seriesList="filteredSeries"
      :languagesList="languagesList" />
  </div>
</template>

<script>
import axios from 'axios'
import HeaderContainer from './components/HeaderContainer.vue'
import MainContainer from './components/MainContainer.vue'

export default {
  name: 'App',
  components: {
    HeaderContainer,
    MainContainer,

  },
  data() {
    return {
      inputResults: [],
      filteredMovies: [],
      filteredSeries: [],
      languagesList: ['it', 'en', 'de', 'fr'],
      api_key: '01092a6fa91a73f0dcb49eff60b71512',

    }
  },
  methods: {
    searchMovie() {
      this.filteredMovies = this.inputResults.filter((element) => {
        return element.media_type === 'movie'
      });
    },
    searchSerie() {
      this.filteredMovies = this.inputResults.filter((element) => {
        return element.media_type === 'tv'
      });
    },
    searchInput(query) {
      const params = {
        query: query,
        api_key: this.api_key
      }

      if(query !== null) {
        return axios.get(`https://api.themoviedb.org/3/search/multi`, {params})
        .then((response) => {
          this.inputResults = response.data.results
        })
      }
    },
    
  }
}
</script>

<style lang="scss">
@import './style/main.scss'
</style>
