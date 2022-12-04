
<!-- pretend this is body.vue then change after -->
<template>
    <div>
        <h2>{{this.songTitle}} by {{this.songArtist}}</h2>
        <button @click="addToPlaylist">Add to Playlist</button>
        <!-- <PlayList v-for="(playlistSongs,i) in songs" 
        :key="i"
        @addSong="addToPlaylist"
        :songTitle="playlistSongs.title"
        :songArtist="playlistSongs.artist"
        /> -->
    </div>
</template>

<script>

export default {
        name : "SongList",
        props : {
            songTitle: String,
            songArtist: String,
        },
        data() {
            return {
                // songs: [
                //     {
                //         title: "Alors on Danse",
                //         artist: "Stromae"
                //     },
                //     {
                //         title: "Scoop",
                //         artist: "Bingo Players & Peyruis"
                //     },
                //     {
                //         title: "Jam",
                //         artist: "Eddy Wata"
                //     },
                //     {
                //         title: "Check",
                //         artist: "Hi-Lo & Will Clarke"
                //     },
                //     {
                //         title: "Low",
                //         artist: "Oliver Heldens, Tchami & Anabel Englund"
                //     },
                //     {
                //         title: "Escape",
                //         artist: "Deadmau5 & Kaskade"
                //     },
                //     {
                //         title: "Lokomotif",
                //         artist: "Hi-Lo"
                //     },
                //     {
                //         title: "Deja Vu",
                //         artist: "Mike Cervello & Curbi"
                //     },
                //     {
                //         title: "Dance With Me",
                //         artist: "Kevin de Vries"
                //     },
                //     {
                //         title: "Cola",
                //         artist: "Camelphat & Elderbrook"
                //     },
                // ],
                // playlist: []
            }
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