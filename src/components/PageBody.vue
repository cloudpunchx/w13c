<template>
    <div >
        <h1>Top EDM 2022</h1>
        <h2>Create your own playlist, music updated weekly!</h2>
        <div class="addToPlaylistDiv">
            <img src="https://cdn-icons-png.flaticon.com/512/2995/2995101.png">
            <p>Add to Playlist</p>
        </div>
        <SongList class="songContainer" v-for="(listSongs,index) in songs"
        :key="index"
        :songTitle="listSongs.title"
        :songArtist="listSongs.artist"
        @addSong="addToPlaylist"
        />
        <PlayList/>
        <!-- <PlayList v-for="(newPlaylist,i) in songs"
        :key="i"
        :playlistSongTitle="newPlaylist.title"
        :playlistSongArtist="newPlaylist.artist"
        /> -->
    </div>
</template>

<script>
import SongList from '@/components/SongList.vue';
import PlayList from '@/components/PlayList.vue';

    export default {
        name : "PageBody",
        components: {
            SongList,
            PlayList
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
                playlist: [],
                // isSelected : "true",
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
h1, h2{
    color: #FF36AB;
    -webkit-text-stroke: .5px white;
}
.songContainer{
    color: #642CA9;
    font-size: .6em;
    /* changed cursor so user would actually know the h2 tags are clickable */
    cursor: pointer;
    background-color: white;
    box-shadow: 0 2px 2px 0 rgba(255, 255, 255, 0.319), 0 2px 2px 0 rgba(255, 255, 255, 0.354);
    border: 2px solid #F42272;
    border-radius: 5px;
    margin: 10px;
    width: 25%;
    position: relative;
    left: 13%;
}
.songContainer:hover{
    color: #00F5D4;
}
img{
    height: 3vh;
    margin-top: 5px;
    margin-right: 4px;
}
.addToPlaylistDiv{
    color: #642CA9;
    font-weight: bold;
    font-size: 1em;
    background-color: white;
    box-shadow: 0 2px 2px 0 rgba(255, 255, 255, 0.319), 0 2px 2px 0 rgba(255, 255, 255, 0.354);
    border: 2px solid #F42272;
    border-radius: 5px;
    padding: 0px 5px;
    height: 10%;
    display: inline-flex;
    /* position: absolute;
    top: 40%;
    left: 45%; */
}
li{
    color: #642CA9;
    font-size: .6em;
    /* changed cursor so user would actually know the h2 tags are clickable */
    cursor: pointer;
    background-color: white;
    box-shadow: 0 2px 2px 0 rgba(255, 255, 255, 0.319), 0 2px 2px 0 rgba(255, 255, 255, 0.354);
    border: 2px solid #F42272;
    border-radius: 5px;
    margin: 10px;
    width: 25%;
    position: relative;
    left: 13%;
}
</style>