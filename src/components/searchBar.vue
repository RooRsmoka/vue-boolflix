<template>
    <div>
        <input 
            type="text"
            placeholder="Search..."
            v-model="textInput"
        >
        <button @click="$emit('search', textInput)">Search</button>
    </div>
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

</style>