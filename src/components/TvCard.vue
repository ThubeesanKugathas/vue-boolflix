<template>
    <div class="ms_card-box position-relative">
        <img :src="`https://image.tmdb.org/t/p/original${show.poster_path}`" :alt="show.name">
        <div class="ms_hover position-absolute top-0 start-0 px-3 py-5">
            <p><strong>Name: </strong>{{show.name}}</p>
            <p><strong>Original Name: </strong>{{show.original_name}}</p>
            <p><strong>Rating: </strong>{{show.vote_average}}</p>
            <p><strong>Originl Language: </strong>{{show.original_language}}</p>
            <p><strong>Overview: </strong>{{show.overview}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        show: Object,
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