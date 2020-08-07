<template>
  <nav>
    <div class="nav-wrapper teal">
      <a href="#!" class="brand-logo hide-on-med-only">COVID-19 Tracker</a>
    </div>
  </nav>
</template>

<script>
import "materialize-css/dist/css/materialize.min.css";
import M from "materialize-css";

export default {
  name: "Nevbar",
  mounted() {
    const elems = document.querySelectorAll(".sidenav");
    M.Sidenav.init(elems, {});
  }
};
</script>

<style scoped>
</style>