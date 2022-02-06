<template>
  <div id="app">
    <header-box  @search="searchTitle"/>
    <empty-main v-if="!flagEmpty" :popularMovies="popularMovies" :popularShows="popularShows"/>
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
      popularMovies: [],
      popularShows: [],
    }
  },
  mounted() {
    axios.get(`https://api.themoviedb.org/3/movie/popular?api_key=0785e92f26ecdb9f62cd6d8a9cbc46ed&page=1`)
      .then((response) => {
        this.popularMovies = response.data.results;
      });

    axios.get(`https://api.themoviedb.org/3/tv/popular?api_key=0785e92f26ecdb9f62cd6d8a9cbc46ed&page=1`)
      .then((response) => {
        this.popularShows = response.data.results;
      });
  },
  methods: {
    searchTitle(input) {
      // movies axios.get
      axios.get(`https://api.themoviedb.org/3/search/movie?query=${input}&api_key=0785e92f26ecdb9f62cd6d8a9cbc46ed`)
        .then((response) => {
          this.movieList = response.data.results;
        });

      // tv shows axios.get
      axios.get(`https://api.themoviedb.org/3/search/tv?query=${input}&api_key=0785e92f26ecdb9f62cd6d8a9cbc46ed`)
        .then((response) => {
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
