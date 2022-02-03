<template>
    <div class="ms_card-box position-relative">
        <img :src="`https://image.tmdb.org/t/p/original${movie.poster_path}`" :alt="movie.title">
        <div class="ms_hover position-absolute top-0 start-0 px-3 py-5">
            <p><strong>Title: </strong>{{movie.title}}</p>
            <p><strong>Original Title: </strong>{{movie.original_title}}</p>
            <p><strong>Rating: </strong>{{movie.vote_average}}</p>
            <p><strong>Originl Language: </strong>{{movie.original_language}}</p>
            <p><strong>Overview: </strong>{{movie.overview}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        movie: Object,
    },
    data() {
        return {
            active: false,
        }
    },
    methods: {
        activeImg() {
            this.active = !this.active;
        }
    }
}
</script>

<style lang="scss" scoped>
    .ms_card-box {
        height: 500px;
        width: calc((100% - 80px) / 3);
        margin: 10px;
        overflow: hidden;

        &:hover .ms_hover {
            display: block;
        }

        img {
            width: 100%;
        }

        .ms_hover {
            background-color: #000;
            height: 100%;
            width: 100%;
            color: #fff;
            overflow-y: auto;
            display: none;

            p {
                margin: 0;
                font-size: 20px;
            }

            strong {
                font-size: 25px;
            }
        }
    }
</style>