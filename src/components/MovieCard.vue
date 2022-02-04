<template>
    <div class="ms_card-box position-relative">
        <h2>MOVIE</h2>
        <img :src="`https://image.tmdb.org/t/p/original${movie.poster_path}`" :alt="movie.title">
        <div class="ms_hover position-absolute top-0 start-0 px-3 py-5">
            <p><strong>Title: </strong>{{movie.title}}</p>
            <p><strong>Original Title: </strong>{{movie.original_title}}</p>
            <p>
                <strong>Rating: </strong>
                <i class="fas fa-star" 
                    v-for="(star, i) in Math.round(movie.vote_average / 2)" 
                    :key="i"></i>
            </p>
            <p>
                <strong>Originl Language: </strong>{{movie.original_language.toUpperCase()}} 
                <img :src="`/flags/${movie.original_language}.png`" :alt="movie.original_language">
            </p>
            <p><strong>Overview: </strong>{{movie.overview}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        movie: Object,
    },
}
</script>

<style lang="scss" scoped>
@import '../style/card.scss';
</style>