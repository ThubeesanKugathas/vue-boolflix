<template>
    <div class="ms_card-box position-relative">
        <h2>TV SHOW</h2>
        <img :src="`https://image.tmdb.org/t/p/original${show.poster_path}`" :alt="show.name">
        <div class="ms_hover position-absolute top-0 start-0 px-3 py-5">
            <p><strong>Name: </strong>{{show.name}}</p>
            <p><strong>Original Name: </strong>{{show.original_name}}</p>
            <p><strong>Rating: </strong>{{show.vote_average}}</p>
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