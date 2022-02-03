<template>
    <header class="d-flex justify-content-between align-items-center p-4">
        <h1>BOOLFLIX</h1>
        <div class="ms_right">
            <input type="text" v-model="title" placeholder="Search">
            <button @click="$emit('search', title)">Search</button>
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
    header {
        background-color: #000;
        height: 80px;

        h1 {
            color: #e00000;
            font-weight: bold;
        }

        .ms_right {
            font-size: 20px;

            input {
                margin-right: 10px;
            }
        }
    }
</style>