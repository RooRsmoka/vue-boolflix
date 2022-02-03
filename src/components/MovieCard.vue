<template>
    <div class="content-card">
        <div class="movie-poster">
            <img :src="`https://image.tmdb.org/t/p/w342/${movie.poster_path}`" :alt="movie.original_title">
        </div>
        <div class="movie-info">
            <p><strong>Title:</strong>  {{movie.title}}</p>
            <p>Original title: {{movie.original_title}}</p>
            <p>Language: {{movie.original_language}}</p>
            <p>Rating: {{movie.vote_average}}</p>
            <p>Overview: {{movie.overview}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        movie: Object
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/movieCard.scss';
</style>