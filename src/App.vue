<template>
  <div
    id="app"
    class="main-app"
  >
    <nav-bar />
    <router-view />
  </div>
</template>

<script>
import NavBar from '@/components/NavBar';

export default {
  components: {
    NavBar,
  },
};
</script>
