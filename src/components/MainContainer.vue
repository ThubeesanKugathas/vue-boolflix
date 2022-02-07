<template>
    <main class="ms_component-container">
        <!-- MOVIES -->
        <h1 v-if="movieList.length > 0">MOVIES</h1>
        <div class="ms_container d-flex">
            <movie-card v-for="movie in movieList" 
                :key="movie.id"
                :movie="movie"/>
        </div>
        <!-- TV SHOWS -->
        <h1 v-if="tvList.length > 0">TV SHOWS</h1>
        <div class="ms_container d-flex">
            <tv-card v-for="show in tvList" 
                :key="show.id"
                :show="show"/>
        </div>
    </main>
</template>

<script>
import MovieCard from '../components/MovieCard.vue'
import TvCard from '../components/TvCard.vue'

export default {
    components: {
        MovieCard,
        TvCard,
    },
    props: {
        movieList: Array,
        tvList: Array,
    },
}
</script>

<style lang="scss" scoped>
    @import '../style/container.scss';
</style>