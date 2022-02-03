<template>
    <div>
        <movie-card
            v-for="(movie, index) in movieList"
            :key="index"
            :movie="movie" />
    </div>
</template>

<script>
import MovieCard from './MovieCard.vue'

export default {
    components: {
        MovieCard,

    },
    props: {
        movieList: Array,

    }
    
}
</script>

<style lang="scss" scoped>

</style>