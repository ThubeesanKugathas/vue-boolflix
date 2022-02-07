<template>
  <div id="app">
    <header-box  @search="searchTitle" @reload="reload"/>
    <popular-shows v-if="!flagEmpty" :popularMovies="popularMovies" :popularShows="popularShows"/>
    <main-container :movieList="movieList" :tvList="tvList"/>
  </div>
</template>

<script>
import axios from 'axios'
import HeaderBox from './components/HeaderBox.vue'
import PopularShows from './components/PopularShows.vue'
import MainContainer from './components/MainContainer.vue'

export default {
  name: 'App',
  components: {
    HeaderBox,
    PopularShows,
    MainContainer,
  },
  data() {
    return {
      api_key: '0785e92f26ecdb9f62cd6d8a9cbc46ed',
      showResults: [],
      flagEmpty: false,
      popularMovies: [],
      popularShows: [],
    }
  },
  mounted() {
    axios.get(`https://api.themoviedb.org/3/movie/popular?api_key=${this.api_key}&page=1`)
      .then((response) => {
        this.popularMovies = response.data.results;
      });

    axios.get(`https://api.themoviedb.org/3/tv/popular?api_key=${this.api_key}&page=1`)
      .then((response) => {
        this.popularShows = response.data.results;
      });
  },
  computed: {
    movieList() {
      let movieList = this.showResults.filter((result) => {
        return result.media_type === 'movie';
      });

      return movieList;
    },
    tvList() {
      let tvList = this.showResults.filter((result) => {
        return result.media_type === 'tv';
      });

      return tvList;
    },
  },
  methods: {
    searchTitle(input) {
      // axios.get multi
      axios.get(`https://api.themoviedb.org/3/search/multi?query=${input}&api_key=${this.api_key}`)
        .then((response) => {
          this.showResults = response.data.results;
        });

      this.flagEmpty = true;
    },
    reload() {
      location.reload();
    }
  }
}
</script>

<style lang="scss">
  @import './style/app.scss';
</style>
