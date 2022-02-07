<template>
    <div>
        <div class="ms_container d-flex justify-content-between flex-wrap">
            <movie-card v-for="popularmovie in popularMovies" 
                :key="popularmovie.id"
                :movie="popularmovie" />
        </div>
        <!-- TV SHOWS -->
        <div class="ms_container d-flex justify-content-between flex-wrap">
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
    div {
        background-color: #222;
        padding: 20px 0 50px;

        h1 {
            margin-left: 100px;
            color: #fff;
        }

        .ms_container {
            width: 1200px;
            margin: 0 auto 100px; 
        }
    }
</style>