<template>
    <div>
        <h2>{{songTitle}} by {{SongArtist}}</h2>
    </div>
</template>

<script>
    export default {
        name : "SongProps",
        props : {
            songTitle: String,
            songArtist: String
        }
    }
</script>

<style scoped>

</style>