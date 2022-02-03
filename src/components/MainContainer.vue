<template>
    <main>
        <!-- MOVIES -->
        <div class="ms_container d-flex justify-content-between flex-wrap">
            <movie-card v-for="movie in movieList" 
                :key="movie.id"
                :movie="movie" />
        </div>
        <!-- TV SHOWS -->
        <div class="ms_container d-flex justify-content-between flex-wrap">
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
    }
}
</script>

<style lang="scss" scoped>
    main {
        background-color: #434343;
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