<template>
    <div>
        <SongList v-for="(playlistSongs,index) in songs"
        :key="index"
        :songTitle="playlistSongs.title"
        :songArtist="playlistSongs.artist"
        @addSong="addToPlaylist"
        />
    </div>
</template>

<script>
import SongList from '@/components/SongList.vue';

    export default {
        name : "PageBody",
        playlist: [],
        components: {
            SongList,
        },
        data() {
            return {
                songs: [
                    {
                        title: "Alors on Danse",
                        artist: "Stromae"
                    },
                    {
                        title: "Scoop",
                        artist: "Bingo Players & Peyruis"
                    },
                    {
                        title: "Jam",
                        artist: "Eddy Wata"
                    },
                    {
                        title: "Check",
                        artist: "Hi-Lo & Will Clarke"
                    },
                    {
                        title: "Low",
                        artist: "Oliver Heldens, Tchami & Anabel Englund"
                    },
                    {
                        title: "Escape",
                        artist: "Deadmau5 & Kaskade"
                    },
                    {
                        title: "Lokomotif",
                        artist: "Hi-Lo"
                    },
                    {
                        title: "Deja Vu",
                        artist: "Mike Cervello & Curbi"
                    },
                    {
                        title: "Dance With Me",
                        artist: "Kevin de Vries"
                    },
                    {
                        title: "Cola",
                        artist: "Camelphat & Elderbrook"
                    },
                ],
                playlist: []
            }
        },
        methods: {
            // function to add selected songs to a new array called Playlist
            addToPlaylist(item) {
                this.playlist.push(item);
            },

        },
    }
</script>

<style scoped>

</style>