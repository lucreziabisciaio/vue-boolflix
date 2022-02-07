<template>
    <div class="header_container text-white d-flex justify-content-between align-items-center p-2">
        <nav class="d-flex align-items-center">
            <div class="logo">
                <a href="#">
                    <img class="w-100" src="https://upload.wikimedia.org/wikipedia/commons/7/7a/Logonetflix.png" alt="">
                </a>
            </div>

            <ul class="list-unstyled my-0">
                <li>Home</li>
                <li>Serie TV</li>
                <li>Film</li>
                <li>Originali</li>
                <li>Aggiunti di recente</li>
                <li>La mia lista</li>
            </ul>

        </nav>

        <div class="search_area d-flex align-items-center">
            <input
                class="text-white"
                type="text"
                placeholder="Search..."
                v-model="keywordSearch"
            />

            <span>
                <i class="fas fa-search" @click="$emit('search', keywordSearch)"></i>
            </span>

            <p class="fw-bold m-0 px-3 text-white">BAMBINI</p>
            <i class="fas fa-bell text-white"></i>
            
        </div>
        
    </div>
</template>

<script>
export default {
    data() {
        return {
            keywordSearch: null,

        }
    }

}
</script>

<style lang="scss" scoped>
@import '@/style/headerContainer.scss'
</style>