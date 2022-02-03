<template>
  <div id="app">
    <header-container />
  </div>
</template>

<script>
import HeaderContainer from './components/HeaderContainer.vue'

export default {
  name: 'App',
  components: {
    HeaderContainer,
    
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
