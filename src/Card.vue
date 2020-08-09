<template>
    <div class="col s12 m4 center">
      <div class="card-panel">
        <i class="material-icons large teal-text">all_inclusive</i>
        <h5>Corona cases</h5>
        <h5 class="red-text">+{{info.todayCases}}</h5>
        <h6>{{info.cases}} Total</h6>
      </div>
    </div>
</template>

<script>
import "materialize-css/dist/css/materialize.min.css";

export default {
  name: "Card",
  props: ["info"]
};
</script>

<style scoped>
</style>