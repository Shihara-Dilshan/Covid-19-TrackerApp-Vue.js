<template>
  <div id="app">
    <Nevbar />
    <br />
    <div class="row">
      <div class="col s12 m8 l9">
        <select v-on:change="getCountry">
          <option value="worldwide">world wide</option>
          <option
            v-bind:value="country.value"
            v-bind:key="country.id"
            v-for="country in countries"
          >{{country.name}}</option>
        </select>
        <div class="row">
          <Card v-bind:info="countryInfo"/>
          <Recorverd v-bind:info="countryInfo"/>
          <Deaths v-bind:info="countryInfo"/>
          <Card /> -->
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
import Card from "./Card.vue";
import Recorverd from './Recorverd.vue';
import Deaths from './Deaths.vue'
import MapImage from "./MapImage.vue";

import M from "materialize-css";

export default {
  name: "App",
  components: {
    Nevbar,
    Card,
    Recorverd,
    Deaths,
    MapImage
  },
  methods: {
    getCountry(e) {
      console.log(e.target.value);
    }
  },
  mounted() {
    const elems = document.querySelectorAll("select");
    M.FormSelect.init(elems, {});
  },
  async created() {
    const apiCall = await fetch("https://www.disease.sh/v3/covid-19/countries");
    const result = await apiCall.json();

    const worldWide = await fetch('https://www.disease.sh/v3/covid-19/all');
    const wolrdWideResult = await worldWide.json();


    const countries = result.map(country => {
      return {
        name: country.country,
        id: country.countryInfo._id,
        value: country.countryInfo.iso2,
        cases: country.cases
      };
    });
    this.countries = countries;
    this.countryInfo = wolrdWideResult;

    const elems = await document.querySelectorAll("select");
    await M.FormSelect.init(elems, {});
  },
  data() {
    return {
      countries: [],
      country: "worldwide",
      countryInfo: {},
      tableData: []
    };
  }
};
</script>

<style>
</style>
