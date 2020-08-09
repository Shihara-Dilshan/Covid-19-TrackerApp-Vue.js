<template>
    <div class="col s12 m4 center">
      <div class="card-panel">
        <i class="material-icons large teal-text">fitness_center</i>
        <h5>Deaths</h5>
        <h5>+{{info.todayDeaths}}</h5>
        <h6>{{info.deaths}} Total</h6>
      </div>
    </div>
</template>

<script>
import "materialize-css/dist/css/materialize.min.css";

export default {
  name: "Deaths",
  props: ["info"]
};
</script>

<style scoped>
</style>