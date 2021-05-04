<template>
  <div class="flex">
    <MusicList @play="play" />
    <Player :currentSong="currentSong" />
  </div>
</template>

<script>
import MusicList from './components/MusicList.vue';
import Player from './components/Player.vue';
export default {
  components: {
    MusicList,
    Player,
  },

  data() {
    return {
      currentSong: 'Broke',
    };
  },

  methods: {
    play(song) {
      this.currentSong = song;
    },
  },
};
</script>

<style></style>
