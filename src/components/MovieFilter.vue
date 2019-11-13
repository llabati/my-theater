<template>
    <div id="movie-filter">
        <h2>Movie Filter</h2>
        <h3>Filter results</h3>
        <div class="filter-group">
            <check-filter v-for="genre in genres" :key="genre.id" :title="genre" @check-filter="checkFilter"></check-filter>
        </div>
    </div>
</template>

<script>
import CheckFilter from '@/components/CheckFilter.vue';
import genres from '../utils/genres.js'
export default {
    props: {
        genres: Object
    },
    data(){
        return {
            genres,
            
        }
    },
    methods: {
        checkFilter(item){
            this.$emit('check-filter', item)
            console.log('event re-emitted!')
        }
    },
    components: {
      CheckFilter
  }  
}
</script>

<style lang="scss" scoped>

</style>