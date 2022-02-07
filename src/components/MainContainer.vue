<template>
    <div class="mx-2">
        <h4 class="text-white fw-bold mt-3 mb-2">MOVIES</h4>
        <div class="movies_container row d-flex align-items-center flex-nowrap">

            <movie-card
                v-for="movie in movieList"
                :key="movie.id"
                :movie="movie"
                :languagesList="languagesList"
            />

        </div>

        <h4 class="text-white fw-bold mt-3 mb-2">TV SHOW</h4>
        <div class="series_container row d-flex align-items-center flex-nowrap">

            <serie-card 
                v-for="serie in seriesList"
                :key="serie.id"
                :serie="serie"
                :languagesList="languagesList"
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
.movies_container,
.series_container {
    overflow-y: hidden;
    overflow-x: scroll;
}
</style>