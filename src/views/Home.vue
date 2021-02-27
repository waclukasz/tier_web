<template>
  <div class="home-slideshow">
    <transition name="fade">
      <div
        v-if="isVideoShown"
        :style="{
          top: videoPosY,
          left: videoPosX
        }"
        class="showreal-container"
      >
        <video 
          class="showreal-video"
          :src="currentVideoSrc && require(`@/assets/videos/${currentVideoSrc}.webm`)"
          autoplay="true"
          muted
          loop
          playsinline
        />
      </div>
    </transition>
    <div class="movies-list-container">
      <div 
        v-for="(movie, index) in movies"
        :key="movie.name"
        class="movie-list-item"
      >
        <div 
          class="index-container"
        >
          <transition name="fade">
            <span 
              v-if="currentVideoSrc === movie.src"
              class="index-border"
            />
          </transition>
          <transition name="fade">
            <div 
              v-if="currentVideoSrc === movie.src"
              class="movie-index"
            >
              {{ index + 1 }}
            </div>
          </transition>
        </div>
        <p
          :class="{ active: currentVideoSrc === movie.src }"
          @mousemove="showVideo($event, movie)"
          @mouseleave="hideVideo()"
        >
          {{ movie.name }}
        </p>
        <transition name="grow">
          <div
            v-if="currentVideoSrc === movie.src"
            class="index-divider"
          />
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
// import gsap from 'gsap';
import MOVIES from '@/mockData/movies';

export default {
  name: 'Home',

  data() {
    return {
      movies: MOVIES,
      currentVideoSrc: undefined,
      isVideoShown: false,
      videoPosY: 0,
      videoPosX: 0,
      slowsDownAccel: 80,
    };
  },

  methods: {
    showVideo(e, video) {
      console.log(this.isNewTransition);
      this.currentVideoSrc = video.src;
      if (!this.isVideoShown) {
        this.videoPosY = `${e.pageY - 100}px`;
        this.videoPosX = `${e.pageX - 100}px`;
      }
      this.isVideoShown = true;
     
      setTimeout(() => {
        this.videoPosY = `${e.pageY - 100}px`;
        this.videoPosX = `${e.pageX - 100}px`;
      }, this.slowsDownAccel);
      
    },
    hideVideo() {
      this.isVideoShown = false;
      this.currentVideoSrc = undefined;
    },
  },
};
</script>