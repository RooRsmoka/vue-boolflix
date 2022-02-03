<template>
    <header>
        <h1>boolflix</h1>
        <div class="search-bar">
            <input 
                type="text"
                placeholder="Search a Movie,TV series..."
                v-model="textInput"
            >
            <button @click="$emit('search', textInput)">Search</button>
        </div>
    </header>
</template>

<script>
export default {
    data() {
        return {
            textInput: ''
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/searchBar.scss';
</style>