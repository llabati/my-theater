<template>
  <div class="home">
    <div id="title">
        <img src="../../public/logo.png">
        <h1>My Vue.js Cinema</h1>
    </div>
    <div id="overview">
      <div id="main">
        <movie-list></movie-list>
        <movie-filter :genres="genres" @check-filter="checkFilter"></movie-filter>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

import MovieList from '../components/MovieList.vue'
import MovieFilter from '@/components/MovieFilter.vue';
import genres from '../utils/genres.js'
export default {
  name: 'home',
  data(){
    return {
      genres,
      selectedGenres: []
    }
  },
  methods: {
    checkFilter(item){
            if (this.selectedGenres.includes(item)) {
                let indexToDelete = this.selectedGenres.indexOf(item)
                this.selectedGenres.splice(indexToDelete, 1)
            }
            else {
                this.selectedGenres = [ ...this.selectedGenres, item]
            }
            console.log('event received!', this.selectedGenres)
        }
  },
  components: {
    MovieList,
    MovieFilter
  }
}
</script>
