<template>
  <div class="MovieView container">
    <p class="lead text-center pt-5"><strong>나만의 무비 컬렉션</strong></p>
    <div class="d-flex justify-content-center py-5">
      <button v-if="showButton" @click="getMovieData" class="btn btn-info text-white"><strong>영화 가져오기</strong></button>
    </div>
    <MovieList :movies="movies"/>
    
  </div>
</template>

<script>
import axios from 'axios'
import MovieList from '@/components/MovieList.vue'

const MOVIE_API_URL = 'https://www.json-generator.com/api/json/get/ceNyuXZmwi?indent=2'
export default {
  name: 'MovieView',
  components: {
    MovieList
  },
  data() {
    return {
      movies: [],
      showButton: true,
    }
  },
  methods: {
    getMovieData() {
      this.showButton = false
      axios.get(MOVIE_API_URL)
      .then(res => {
        this.movies = res.data
        console.log(this.movies)
      })
      .catch(err => {
        console.log(err)
      })
    }
  }
}
</script>
