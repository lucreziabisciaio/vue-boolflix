<template>
  <div id="app">
    <header-container />
    <main-container />
  </div>
</template>

<script>
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
    
  }
}
</script>

<style lang="scss">

</style>
