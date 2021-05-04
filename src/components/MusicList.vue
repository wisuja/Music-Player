<template>
  <div class="flex-none w-96">
    <div class="bg-blue-400 p-4">
      <h1 class="font-bold text-2xl text-center text-white">Music List</h1>
    </div>
    <div :class="classes">
      <Music
        v-for="(song, index) in songs"
        :key="index"
        :song="song"
        :currentSong="currentSong"
        @play="play"
      ></Music>
    </div>
  </div>
</template>

<script>
import Music from './Music.vue';

export default {
  data() {
    return {
      songs: ['Broke', 'Love is gone', 'Overwhelmed'],
      currentSong: 'Broke',
    };
  },
  components: {
    Music,
  },
  methods: {
    play(song) {
      this.currentSong = song;
      this.$emit('play', song);
    },
  },
};
</script>

<style>
.closed {
  transform: translateX(-100%);
}
</style>
