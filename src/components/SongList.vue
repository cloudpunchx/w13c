<template>
    <div>
        <li @click="addToPlaylist">{{this.songTitle}} by {{this.songArtist}}</li>
    </div>
</template>

<script>

export default {
        name : "SongList",
        props : {
            songTitle: String,
            songArtist: String,
        },
        methods: {
            addToPlaylist() {
                this.$emit(`addSong`, this.songTitle, this.songArtist)
            },
        },
    }
</script>

<style scoped>
li{
    list-style-type: none;
}
</style>