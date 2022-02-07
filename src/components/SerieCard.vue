<template>
    <div class="serie_card border border-white overflow-hidden m-2">
        <div class="serie_info h-100 w-100 text-white p-3 bg-dark">
            <div>{{serie.title}}</div>
            <div>{{serie.original_title}}</div>

            <!-- flags -->
            <div v-if="!languagesList.includes(serie.original_language)">{{serie.original_language}}</div>
            <div v-else>
                <img :src="`/flags/${serie.original_language}.png`" alt="" />
            </div>
            <!-- stars -->
            <div>
                <stars-classification :vote="serie.vote_average"/>
            </div>

            <div>{{serie.overview}}</div>
        </div>

        <div class="serie_poster">
            <img class="w-100" :src="getImg()" alt="" />
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
        serie: Object,
        languagesList: Array,

    },
    methods: {
        getImg() {
            if (this.serie.poster_path !== null) {
               return `http://image.tmdb.org/t/p/w342/${this.serie.poster_path}` 
            } else {
                return `https://www.2queue.com/2queue/wp-content/uploads/sites/6/tdomf/4299/movie-poster-coming-soon.png`
            }
        }
    }
    
}
</script>

<style lang="scss" scoped>
.serie_card {
    width: 342px;
    height: 450px;

    position: relative;

    &:hover .serie_info {
        display: block;
    }

    .serie_info {
        display: none;
        position: absolute;
        overflow: auto;
        opacity: 0.9;
    }
}
</style>