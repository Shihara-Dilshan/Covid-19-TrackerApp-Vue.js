<template>
  <div id="app">
    <Nevbar />
  </div>
</template>


<script>
import "materialize-css/dist/css/materialize.min.css";
import Nevbar from './Nevbar.vue'

export default {
  name: "App",
  components: {
    Nevbar
  },
  data(){
    return{
      api_key: '',
    }
  }
};
</script>

<style>
 
</style>
