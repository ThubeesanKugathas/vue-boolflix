<template>
    <div class="ms_card-box position-relative">
        <h2>TV SHOW</h2>
        <img :src="`https://image.tmdb.org/t/p/original${show.poster_path}`" :alt="show.name">
        <div class="ms_hover position-absolute top-0 start-0 px-3 py-5">
            <p><strong>Name: </strong>{{show.name}}</p>
            <p><strong>Original Name: </strong>{{show.original_name}}</p>
            <div class="d-flex align-items-center">
                <p>
                    <strong>Rating: </strong>
                </p>
                <i class="fas fa-star" 
                    v-for="(star, i) in Math.round(show.vote_average / 2)" 
                    :key="i">
                </i>
                <div v-if="(5 - Math.round(show.vote_average / 2)) > 0">
                    <i class="far fa-star"
                        v-for="(nostar, index) in (5 - Math.round(show.vote_average / 2))"
                        :key="index"></i>
                </div>
            </div>
            <p>
                <strong>Originl Language: </strong>{{show.original_language.toUpperCase()}} 
                <img :src="`/flags/${show.original_language}.png`" :alt="show.original_language">
            </p>
            <p><strong>Overview: </strong>{{show.overview}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        show: Object,
    },
}
</script>

<style lang="scss" scoped>
@import '../style/card.scss';
</style>