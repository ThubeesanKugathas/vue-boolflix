<template>
    <div class="d-flex align-items-center">
        <i class="fas fa-star" v-for="(star, i) in totStars" :key="i"></i>
        <div v-if="(5 - totStars) > 0">
            <i class="far fa-star" v-for="(nostar, index) in (5 - totStars)" :key="index"></i>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        rate: Number,
    },
    computed: {
        totStars() {
            let stars = Math.round(this.rate / 2);

            return stars;
        }
    }
}
</script>

<style lang="scss" scoped>
    @import url('https://use.fontawesome.com/releases/v5.7.1/css/all.css');
    @import '~bootstrap/scss/bootstrap.scss';

    i {
        color: yellow;
    }
</style>