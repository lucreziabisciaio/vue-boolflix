<template>
  <div id="app">
    <header-container @search="searchInput" />
    <main-container :movieList="searchResultList" />
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
      seriesList: [],
      searchResultList: [],
      api_key: '01092a6fa91a73f0dcb49eff60b71512',

    }
  },
  methods: {
    // funzione di ricerca dei FILM all'interno dell'api
    // k = keywordSearch in v-model
    searchMovie(k) {
      const params = {
        query: k,
        api_key: this.api_key
      }

      return axios.get(`https://api.themoviedb.org/3/search/movie`, {params})
      .then((response) => {
        this.movieList = response.data.results
        this.mergeArrays()
      })
    },
    // funzione di ricerca delle SERIE TV
    // k = keywordSearch in v-model
    searchSerie(k) {
      const params = {
        query: k,
        api_key: this.api_key
      }

      return axios.get(`https://api.themoviedb.org/3/search/tv`, {params})
      .then((response) => {
        this.seriesList = response.data.results
        this.mergeArrays()
      })
    }, 
    // funzione che unisce i due array (film, serie tv) (to fix?)
    mergeArrays() {
      return this.searchResultList = [...this.movieList, ...this.seriesList]
    },
    // richiamo le due funzioni di ricerca per inviarle al @search
    // all'interno dell'header-container
    searchInput(k) {
      this.searchMovie(k)
      this.searchSerie(k)
    }
    
  }
}
</script>

<style lang="scss">
@import './style/main.scss'
</style>
