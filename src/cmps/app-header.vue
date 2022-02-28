<template>
  <section class="app-header-container main-container">
    <header class="app-header flex align-center space-between">
      <div class="logo-container">
        <router-link to="/">
          <h1>Weather App</h1>
        </router-link>
      </div>
      <div class="nav-bar-container">
        <nav class="nav-bar flex align-center space-between">
          <router-link to="/">Home</router-link>
          <router-link to="/favorites">Favorites</router-link>
        </nav>
      </div>
    </header>
  </section>
</template>

<script>
export default {
  components: {},
  methods: {},
  computed: {},
};
</script>
