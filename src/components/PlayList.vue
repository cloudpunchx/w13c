<!-- need this page to grab new array (playlist) -->
<!-- and show data within new div playlist -->
<!-- remove from songlist IF isInPlaylist = true -->
<!-- flip for reverse -->

<template>
    <div class="playlistContainer">
        <li>{{this.playlistSongTitle}}{{this.playlistSongArtist}}</li>
    </div>
</template>

<script>
    export default {
        name : "PlayList",
        props : {
            playlistSongTitle: String,
            playlistSongArtist: String,
        },
        // methods: {

        // },
    }
</script>

<style scoped>
.playlistContainer{
    color: #642CA9;
    /* font-size: .6em; */
    /* changed cursor so user would actually know the h2 tags are clickable */
    cursor: pointer;
    background-color: white;
    box-shadow: 0 2px 2px 0 rgba(255, 255, 255, 0.319), 0 2px 2px 0 rgba(255, 255, 255, 0.354);
    border: 2px solid #F42272;
    border-radius: 5px;
    margin: 10px;
    /* position: relative; */
    /* top: 50%; */
}
li{
    list-style-type: none;
}
</style>