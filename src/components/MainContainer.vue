<template>
    <div>
        <p class="text-white">MOVIES</p>
        <div class="container d-flex justify-content-between align-items-center flex-wrap">

            <movie-card :languagesList="languagesList"
                v-for="movie in movieList"
                :key="movie.id"
                :movie="movie"
            />

        </div>

        <p class="text-white">TV SHOW</p>
        <div class="container d-flex justify-content-between align-items-center flex-wrap">

            <serie-card :languagesList="languagesList"
                v-for="serie in seriesList"
                :key="serie.id"
                :serie="serie"
            />

        </div>
    </div>
</template>

<script>
import MovieCard from './MovieCard.vue'
import SerieCard from './SerieCard.vue'

export default {
    components: {
        MovieCard,
        SerieCard,

    },
    props: {
        movieList: Array,
        seriesList: Array,
        languagesList: Array,
        
    }
    
}
</script>

<style lang="scss" scoped>

</style>