<template>
    <div>
        <input 
            type="text"
            placeholder="Search..." 
            v-model="keywordSearch"
            />

        <span>
            <button
                @click="$emit('search', keywordSearch)">Search!</button>
        </span>
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