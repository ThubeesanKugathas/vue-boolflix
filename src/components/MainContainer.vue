<template>
    <main>
        <div class="ms_container d-flex justify-content-between flex-wrap">
            <card-box v-for="movie in movieList" ù
                :key="movie.id"
                :movie="movie" />
        </div>
    </main>
</template>

<script>
import CardBox from '../components/CardBox.vue'

export default {
    components: {
        CardBox,
    },
    props: {
        movieList: Array,
    }
}
</script>

<style lang="scss" scoped>
    main {
        background-color: #434343;
        padding: 20px 0 50px;

        .ms_container {
            width: 1200px;
            margin: 0 auto;
        }
    }
</style>