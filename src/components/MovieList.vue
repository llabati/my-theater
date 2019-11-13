<template>
    <div id="movie-list">
        <h2>Movie List</h2>
        <div v-for="movie in movies" :key="movie.id" class="movie">{{ movie.title }}</div>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                movies: [
                    { title: 'Pulp Fiction' },
                    { title: 'Mulholland Drive' },
                    { title: 'Heat' }
                ]
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>
