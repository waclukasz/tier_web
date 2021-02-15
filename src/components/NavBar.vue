<template>
  <div class="navbar">
    <ul class="d-flex justify-between white font-2">
      <li class="navbar-item">
        <router-link
          to="/"
          active-class="active"
          exact
        >
          Home
        </router-link>
      </li>
      <li class="navbar-item">
        <router-link
          to="/portfolio"
          active-class="active"
          exact
        >
          Portfolio
        </router-link>
      </li>
      <li class="navbar-item">
        <router-link
          to="about"
          active-class="active"
          exact
        >
          About
        </router-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'NavBar',
};
</script>
