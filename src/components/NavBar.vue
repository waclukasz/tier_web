<template>
  <div class="navbar">
    <ul class="d-flex justify-end white font-2">
      <li class="navbar-item">
        <button
          class="menu"
          :class="{active: isMenuActive}"
          @click="toggleMenuClass()"
        >
          <svg viewBox="0 0 64 48">
            <path d="M19,15 L45,15 C70,15 58,-2 49.0177126,7 L19,37"></path>
            <path d="M19,24 L45,24 C61.2371586,24 57,49 41,33 L32,24"></path>
            <path d="M45,33 L19,33 C-8,33 6,-2 22,14 L45,37"></path>
          </svg>
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'NavBar',
  data() {
    return {
      isMenuActive: false,
    };
  },
  methods: {
    toggleMenuClass() {
      this.isMenuActive = !this.isMenuActive;
    },
  },
};
</script>
