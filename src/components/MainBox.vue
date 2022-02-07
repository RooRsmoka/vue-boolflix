<template>
    <main class="container">
        <movie-card v-for="movie in searchedMovies" :key="movie.id" :movie="movie"/>
        <serie-card v-for="serie in searchedSeries" :key="serie.id" :serie="serie"/>
    </main>
</template>

<script>
import MovieCard from './MovieCard.vue'
import SerieCard from './SerieCard.vue'
export default {
    components: {
        MovieCard,
        SerieCard
    },
    props: {
        searchedMovies: Array,
        searchedSeries: Array,
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/mainBox.scss';
</style>