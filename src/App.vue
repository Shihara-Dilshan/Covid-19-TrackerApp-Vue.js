<template>
  <div id="app">
    <Nevbar />
    <br />
    <div class="row">
      <div class="col s12 m8 l9">
        <select >
          <option value="12">sd</option>
          <option value="12">sd</option>
          <option value="12">sd</option>

        </select>
        <div class="row">
          <Card />
          <Card />
          <Card />
        </div>
        <MapImage />
      </div>

      <div class="col s12 m4 l3">
        <h5 class="center">Live cases</h5>
        <table class="striped">
          <tbody>
            <tr>
              <td class="center center-align">eer</td>
              <td class="center center-align">sd</td>
            </tr>
            <tr>
              <td class="center center-align">eer</td>
              <td class="center center-align">sd</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>


<script>
import "materialize-css/dist/css/materialize.min.css";
import Nevbar from "./Nevbar.vue";
import Card from './Card.vue'
import MapImage from './MapImage.vue'
import M from 'materialize-css';

export default {
  name: "App",
  components: {
    Nevbar,
    Card,
    MapImage
  },
  mounted() {
    const elems = document.querySelectorAll('select');
    M.FormSelect.init(elems, {});
  },
  data() {
    return {
      api_key: ""
    };
  }
};
</script>

<style>
</style>
