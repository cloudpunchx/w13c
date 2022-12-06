<template>
    <div >
        <h1>Top EDM 2022</h1>
        <h2>Create your own playlist, music updated weekly!</h2>

        <div>
            <p class="ptag1">EDM</p>
        <!-- Used Props to connect Song List component to Page Body -->
            <SongList class="songContainer" v-for="(listSongs,index) in songs"
                :key="index"
                :songTitle="listSongs.title"
                :songArtist="listSongs.artist"
                :isSelected:="listSongs.isSelected"
                @addSong="addToPlaylist"
            />
        </div>


        <!-- P Tag only appears when Playlist array is 0 -->
        <p class="ptag2" v-if="playlist.length == 0">Select songs for your playlist!</p>
        <!-- Playlist only Shows when Playlist is 1 or more (still remains in DOM, not like v-if) -->
        <PlayList v-show="playlist.length >= 1" 
            v-for="songs in songs" 
            :key="songs.id"
            :playlistSongTitle="songs.songTitle"
            :playlistSongArtist="songs.songArtist"
            v-bind:playlist="playlist"
            />
        

        <!-- <PlayList v-if="songs.isSelected"
        :playlistSongTitle="songs.title"
        :playlistSongArtist="songs.artist"
        /> -->
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
                        artist: "Stromae",
                        id: 100
                    },
                    {
                        title: "Scoop",
                        artist: "Bingo Players & Peyruis",
                        id: 101
                    },
                    {
                        title: "Jam",
                        artist: "Eddy Wata",
                        id: 102
                    },
                    {
                        title: "Check",
                        artist: "Hi-Lo & Will Clarke",
                        id: 103
                    },
                    {
                        title: "Low",
                        artist: "Oliver Heldens, Tchami & Anabel Englund",
                        id: 104
                    },
                    {
                        title: "Escape",
                        artist: "Deadmau5 & Kaskade",
                        id: 105
                    },
                    {
                        title: "Lokomotif",
                        artist: "Hi-Lo",
                        id: 106
                    },
                    {
                        title: "Deja Vu",
                        artist: "Mike Cervello & Curbi",
                        id: 107
                    },
                    {
                        title: "Dance With Me",
                        artist: "Kevin de Vries",
                        id: 108
                    },
                    {
                        title: "Cola",
                        artist: "Camelphat & Elderbrook",
                        id: 109
                    },
                ],
                playlist: [],
            }
        },
        methods: {
            // function to add selected songs to a new array called Playlist
            addToPlaylist(item) {
                this.playlist.push(item);
                console.log('playlist');
            },
        },
    }
</script>

<style scoped>
h1, h2, p{
    color: #FF36AB;
    -webkit-text-stroke: .5px white;
}
h2{
    margin-bottom: 42px;
}
.ptag2{
    position: absolute;
    top: 20%;
    right: 20%;
}
.ptag1{
    position: relative;
    left: -23%;
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