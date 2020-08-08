<template>
  <div id="app">
    <Nevbar />
    <br />
    <div class="row">
      <div class="col s12 m8 l9">
        <select v-on:change="getCountry">
          <option value="worldwide">world wide</option>
          
          

        </select>
        <div v-bind:key="country.id" v-for="country in this.countries">
            <h3 value="dffd">{{country.name}}</h3>
          </div>
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
  methods:{
    getCountry(){
      
    }
  },
  mounted() {
    const elems = document.querySelectorAll('select');
    M.FormSelect.init(elems, {});
  },
  async created(){
    const apiCall = await fetch('https://www.disease.sh/v3/covid-19/countries');
    const result = await apiCall.json();

    const countries = result.map( country => {
      return {
        name: country.country,
        id: country.countryInfo._id,
        value: country.countryInfo.iso2,
        cases: country.cases,
      }
    });
    this.countries = countries;
    
  
  },
  data() {
    return {
      countries: [],
      country: "worldwide",
      countryInfo: {},
      tableData: [],
    };
  }
};
</script>

<style>
</style>
