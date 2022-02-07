<template>
    <div class="ms_card-box position-relative">
        <img :src="`https://image.tmdb.org/t/p/original${show.poster_path}`" :alt="show.name">
        <div class="ms_hover position-absolute top-0 start-0 px-3 py-5">
            <p><strong>Name: </strong>{{show.name}}</p>
            <p><strong>Original Name: </strong>{{show.original_name}}</p>
            <div class="d-flex align-items-center">
                <p><strong>Rating: </strong></p>
                <star-rate :rate="show.vote_average"/>
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
import StarRate from './StarRate.vue'

export default {
    components: {
        StarRate,
    },
    props: {
        show: Object,
    },
}
</script>

<style lang="scss" scoped>
@import '../style/card.scss';
</style>