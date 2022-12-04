<template>
    <div>
        <h2>{{songTitle}}{{songArtist}}</h2>
        <!-- <button @click="addToPlaylist">Add to Playlist</button> -->
    </div>
</template>

<script>
    export default {
        name : "PlayList",
        props : {
            songTitle: String,
            songArtist: String,
        },
        methods: {
            addToPlaylist() {
                this.$emit(`addSong`, this.songTitle, this.songArtist)
            }
        },
    }
</script>

<style scoped>

</style>