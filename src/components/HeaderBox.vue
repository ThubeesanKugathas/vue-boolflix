<template>
    <header class="d-flex justify-content-between align-items-center p-3">
        <div class="ms_left d-flex align-items-center">
            <img src="../assets/netflix-logo.png" alt="netflix-logo">
            <ul class="d-flex m-0">
                <li><a href="#/" @click="$emit('reload')">Home</a></li>
                <li><a href="#/">Serie Tv</a></li>
                <li><a href="#/">Film</a></li>
                <li><a href="#/">Originali</a></li>
                <li><a href="#/">Aggiunti di recente</a></li>
                <li><a href="#/">La mia lista</a></li>
            </ul>
        </div>
        <div class="ms_right">
            <input type="text" v-model="title" placeholder="Search">
            <i class="fas fa-search" @click="$emit('search', title)"></i>
        </div>
    </header>
</template>

<script>
export default {
    data() {
        return {
            title: '',
        }
    },
    methods: {}
}
</script>

<style lang="scss" scoped>
    @import '../style/header.scss';
</style>