<template>
    <div class="movie_card border-0 overflow-hidden">
        <div class="movie_info h-100 w-100 text-white p-3 bg-dark">
            <div>Titolo: {{movie.title}}</div>
            <div v-if="!movie.original_title === movie.title">TItolo originale: {{movie.original_title}}</div>

            <!-- flags -->
            <div v-if="!languagesList.includes(movie.original_language)">{{movie.original_language}}</div>
            <div v-else>
                <img :src="`/flags/${movie.original_language}.png`" alt="" />
            </div>
            <!-- stars -->
            <div>
                <span class="me-2">Voto:</span><stars-classification :vote="movie.vote_average"/>
            </div>

            <div>{{movie.overview}}</div>
        </div>

        <div class="movie_poster">
            <img class="img-fluid" :src="getImg()" alt="" />
        </div>
    </div>
</template>

<script>
import StarsClassification from './StarsClassification.vue'

export default {
    components: {
        StarsClassification,
    },
    props: {
        movie: Object,
        languagesList: Array,

    },
    methods: {
        getImg() {
            if (this.movie.poster_path !== null) {
               return `http://image.tmdb.org/t/p/w342/${this.movie.poster_path}` 
            } else {
                return `https://www.2queue.com/2queue/wp-content/uploads/sites/6/tdomf/4299/movie-poster-coming-soon.png`
            }
        }
    }
    
}
</script>

<style lang="scss" scoped>
.movie_card {
    width: 342px;
    height: 450px;

    position: relative;

    &:hover .movie_info {
        display: block;
    }

    .movie_info {
        display: none;
        position: absolute;
        overflow: auto;
        opacity: 0.9;
    }
}
</style>