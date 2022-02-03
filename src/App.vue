<template>
  <div id="app">
    <header-box  @search="searchTitle"/>
    <empty-main v-if="!flagEmpty"/>
    <main-container :movieList="movieList" :tvList="tvList"/>
  </div>
</template>

<script>
import axios from 'axios'
import HeaderBox from './components/HeaderBox.vue'
import EmptyMain from './components/EmptyMain.vue'
import MainContainer from './components/MainContainer.vue'

export default {
  name: 'App',
  components: {
    HeaderBox,
    EmptyMain,
    MainContainer,
  },
  data() {
    return {
      movieList: [],
      tvList: [],
      flagEmpty: false,
    }
  },
  methods: {
    searchTitle(input) {
      axios.get(`https://api.themoviedb.org/3/search/movie?query=${input}&api_key=0785e92f26ecdb9f62cd6d8a9cbc46ed`).then((response) => {
        this.movieList = response.data.results;
      });

      axios.get(`https://api.themoviedb.org/3/search/tv?query=${input}&api_key=0785e92f26ecdb9f62cd6d8a9cbc46ed`).then((response) => {
        this.tvList = response.data.results;
      });

      this.flagEmpty = true;
    }
  }
}
</script>

<style lang="scss">
  @import './style/app.scss';
</style>
