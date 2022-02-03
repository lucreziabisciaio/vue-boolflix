<template>
    <div class="header_container d-flex justify-content-between align-items-center p-2 bg-dark">
        <div class="logo">
            <div class="text-danger fs-4 fw-bolder">BOOLFLIX</div>
        </div>

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
            keywordSearch: "",

        }
    }

}
</script>

<style lang="scss" scoped>

</style>