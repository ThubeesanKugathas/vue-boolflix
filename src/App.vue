<template>
  <div id="app">
    <header-box  @search="searchMovie"/>
    <main-container :movieList="movieList"/>
  </div>
</template>

<script>
import axios from 'axios'
import HeaderBox from './components/HeaderBox.vue'
import MainContainer from './components/MainContainer.vue'

export default {
  name: 'App',
  components: {
    HeaderBox,
    MainContainer,
  },
  data() {
    return {
      movieList: [],
    }
  },
  methods: {
    searchMovie(input) {
      axios.get(`https://api.themoviedb.org/3/search/movie?query=${input}&api_key=0785e92f26ecdb9f62cd6d8a9cbc46ed`).then((response) => {
        console.log(response.data.results);
        this.movieList = response.data.results;
      });
    }
  }
}
</script>

<style lang="scss">
  @import './style/app.scss';
</style>
