<template>
    <div class="content-card">
        <div class="content-poster">
            <img :src="`https://image.tmdb.org/t/p/w342/${serie.poster_path}`" :alt="serie.original_name">
        </div>
        <div class="content-info">
            <p>Title: {{serie.name}}</p>
            <p>Original title: {{serie.original_name}}</p>
            <p>
                Language: {{serie.original_language.toUpperCase()}}
                <img :src="`/flags/${serie.original_language}.png`">
            </p>
            <p>Rating: {{serie.vote_average}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        serie: Object,
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/contentCard.scss';
</style>