<template>
    <div class="col s12 m4 center">
      <div class="card-panel">
        <i class="material-icons large teal-text">insert_emoticon</i>
        <h5>Recovered</h5>
        <h5>+{{info.todayRecovered}}</h5>
        <h6>{{info.recovered}} Total</h6>
      </div>
    </div>
</template>

<script>
import "materialize-css/dist/css/materialize.min.css";

export default {
  name: "Recorverd",
  props: ["info"]
};
</script>

<style scoped>
</style>