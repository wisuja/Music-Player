<template>
  <div :class="classes">
    <div class="flex cursor-pointer" @click="play">
      <img :src="profile" alt="profile-picture" class="rounded-full w-8" />
      <h4 class="text-xl ml-3">
        {{ song }}
      </h4>
    </div>
    <h6
      class="text-lg font-medium hover:text-blue-500 cursor-pointer"
      @click="play"
    >
      Play
    </h6>
  </div>
</template>

<script>
import profile from '../assets/images/ryan-mack.jpg';
export default {
  props: ['song', 'currentSong'],
  data() {
    return {
      profile,
    };
  },
  methods: {
    play() {
      this.$emit('play', this.song);
    },
  },
  computed: {
    classes() {
      if (this.currentSong == this.song) {
        return 'p-4 flex border-b-2 border-gray-300 border-opacity-50 align-center justify-between hover:bg-gray-300 transform hover:scale-110 bg-blue-200';
      } else {
        return 'p-4 flex border-b-2 border-gray-300 border-opacity-50 align-center justify-between hover:bg-gray-300 transform hover:scale-110';
      }
    },
  },
};
</script>
