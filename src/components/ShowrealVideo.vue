<template>
  <div class="movie-container">
    <video
      class="movie"
      :src="require(`@/assets/videos/${video.src}.webm`)"
      :width="video.xl"
      :height="video.height || 'auto'"
      :style="{
        left: `calc(${video.position})`
      }"
      autoplay="true"
      muted
      loop
      playsinline
    >
    </video>
  </div>
</template>

<script>
export default {
  name: 'ShowrealVideo',
  props: {
    video: {
      required: true,
      type: Object,
    },
  },
};
</script>