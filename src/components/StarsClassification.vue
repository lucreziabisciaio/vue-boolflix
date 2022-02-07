<template>
    <span>
        <i v-for="(star, index) in stars" :key="index" class="far fa-star"></i>
    </span>
</template>

<script>
export default {
    props: {
        vote: Number,

    },
    computed: {
        stars() {
            return Math.ceil(this.vote / 2)
        }
    }
}
</script>

<style lang="scss" scoped>

</style>