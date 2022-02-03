<template>
    <main class="container">
        <movie-card v-for="movie in movies" :key="movie.id" :movie="movie"/>
    </main>
</template>

<script>
import MovieCard from './MovieCard.vue'
export default {
    components: {
        MovieCard
    },
    props: {
        movies: Array
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/mainContainer.scss';
</style>