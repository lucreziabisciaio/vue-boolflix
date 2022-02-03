<template>
  <div id="app">
    <header-container @search="searchMovie" />
    <main-container :movieList="movieList" />
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
      movieList: [],

    }
  },
  methods: {
    // funzione di ricerca all'interno dell'api
    // k = keywordSearch in v-model
    searchMovie(k) {
      return axios.get(`https://api.themoviedb.org/3/search/movie?query=${k}&api_key=01092a6fa91a73f0dcb49eff60b71512`)
      .then((response) => {
        this.movieList = response.data.results
      })
    },
    
  }
}
</script>

<style lang="scss">

</style>
