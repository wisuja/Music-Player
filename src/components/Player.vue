<template>
  <div
    class="flex flex-1 justify-center items-center min-h-screen flex-col bg-blue-100"
  >
    <div class="relative">
      <img
        src="../assets/images/ryan-mack.jpg"
        alt=""
        class="rounded-full w-24 animate-spin"
      />
      <img
        src="https://i.pinimg.com/originals/de/58/4d/de584db3307b8631ddde6b432830dbcf.gif"
        alt=""
        class="rounded-full w-8 absolute top-0 right-0"
      />
    </div>
    <h1 class="mb-3">Ryan Mack - {{ currentSong }}</h1>
    <div class="flex">
      <audio controls autoplay loop ref="audio">
        <source :src="src" type="audio/mpeg" />
        Your browser does not support the audio element.
      </audio>
    </div>
  </div>
</template>

<script>
export default {
  props: ['currentSong'],
  computed: {
    src() {
      return 'src/assets/songs/' + this.currentSong + '.mp3';
    },
  },
  updated() {
    this.$refs.audio.src = this.src;
    this.$refs.audio.play();
  },
};
</script>
