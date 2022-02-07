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

        <div class="search_area">
            <input
                type="text"
                placeholder="Search..."
                v-model="keywordSearch"
            />

            <span>
                <button
                    @click="$emit('search', keywordSearch)">Search</button>
            </span>
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
.logo {
    width: 150px;

    a {
        cursor: pointer;
    }
}

nav ul {
    margin: 0 35px;

    li {
        display: inline;
        margin: 0 10px;
        cursor: pointer;
    }
}
</style>