<script>
export default {
  data() {
    return {
      routes: [],
    };
  },
  created() {
    this.$router.options.routes.forEach((route) => {
      this.routes.push({
        name: route.name,
        path: route.path,
      });
    });
  },
};
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark fixed-top p-2">
    <a class="navbar-brand text-uppercase" href="#"
      >Parcial Programaci&oacute;n IV</a
    >
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarNav"
      aria-controls="navbarNav"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item active" v-for="route in routes" :key="route">
          <router-link :to="route.path" class="nav-link">{{
            route.name
          }}</router-link>
        </li>
      </ul>
    </div>
  </nav>
</template>
