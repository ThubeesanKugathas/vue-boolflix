<template>
    <header>
        <input type="text" v-model="movie">
        <button @click="$emit('search', movie)">Cerca</button>
    </header>
</template>

<script>
export default {
    data() {
        return {
            movie: '',
        }
    },
    methods: {}
}
</script>

<style lang="scss" scoped>

</style>