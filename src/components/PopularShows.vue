<template>
    <div class="ms_component-container">
        <!-- POPULAR MOVIES -->
        <h1 v-if="popularMovies.length > 0">POPULAR MOVIES</h1>
        <div class="ms_container d-flex">
            <movie-card v-for="popularmovie in popularMovies" 
                :key="popularmovie.id"
                :movie="popularmovie" />
        </div>
        <!-- TV SHOWS -->
        <h1 v-if="popularShows.length > 0">POPULAR TV SHOWS</h1>
        <div class="ms_container d-flex">
            <tv-card v-for="popularshow in popularShows" 
                :key="popularshow.id"
                :show="popularshow"/>
        </div>
    </div>
</template>

<script>
import MovieCard from './MovieCard.vue'
import TvCard from './TvCard.vue'

export default {
    components: {
        MovieCard,
        TvCard,
    },
    props: {
        popularMovies: Array,
        popularShows: Array,
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/container.scss';
</style>