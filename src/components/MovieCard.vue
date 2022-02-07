<template>
    <div class="ms_card-box position-relative">
        <img :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" :alt="movie.title">
        <div class="ms_hover position-absolute top-0 start-0 px-3 py-5">
            <p><strong>Title: </strong>{{movie.title}}</p>
            <p><strong>Original Title: </strong>{{movie.original_title}}</p>
            <div class="d-flex align-items-center">
                <p><strong>Rating: </strong></p>
                <star-rate :rate="movie.vote_average"/>
            </div>
            <p>
                <strong>Originl Language: </strong>{{movie.original_language.toUpperCase()}} 
                <img :src="`/flags/${movie.original_language}.png`" :alt="movie.original_language">
            </p>
            <p><strong>Overview: </strong>{{movie.overview}}</p>
        </div>
    </div>
</template>

<script>
import StarRate from './StarRate.vue'

export default {
    components: {
        StarRate,
    },
    props: {
        movie: Object,
    },
}
</script>

<style lang="scss" scoped>
    @import '../style/card.scss';
</style>