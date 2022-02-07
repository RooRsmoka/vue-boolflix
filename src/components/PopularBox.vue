<template>
    <main class="container">
        <h1 class="cards-title">Popular Movies</h1>
        <div class="cards-container">
            <movie-card v-for="popularMovie in popularMovies" :key="popularMovie.id" :movie="popularMovie"/>
        </div>
        <h1 class="cards-title">Popular Series TV</h1>
        <div class="cards-container">
            <serie-card v-for="popularSerie in popularSeries" :key="popularSerie.id" :serie="popularSerie"/>
        </div>
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
        popularMovies: Array,
        popularSeries: Array
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/popularBox.scss';
</style>