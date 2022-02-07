<template>
    <div class="content-card">
        <div class="content-poster">
            <img :src="`https://image.tmdb.org/t/p/w342/${movie.poster_path}`" :alt="movie.original_title">
        </div>
        <div class="content-info">
            <p>Title: {{movie.title}}</p>
            <p>Original title: {{movie.original_title}}</p>
            <p>
                Language: {{movie.original_language.toUpperCase()}}
                <img :src="`/flags/${movie.original_language}.png`" alt="">
            </p>
            <p>Rating: {{movie.vote_average}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        movie: Object,
    },
}
</script>

<style lang="scss" scoped>
@import '@/style/contentCard.scss';
</style>