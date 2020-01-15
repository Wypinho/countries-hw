<template>
  <div id="app">
    <h1>Countries</h1>
    <country-select :countries='countries'></country-select>
  </div>
</template>

<script>
import { eventBus } from './main.js';
import CountrySelect from './components/CountrySelect.vue';

export default {
  name: 'app',
  data() {
    return {
      countries: [],
      selectedCountry: {}
    }
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
      .then(response => response.json())
      .then(countryArray => this.countries = countryArray)

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    });
  },
  components: {
    "country-select": CountrySelect
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
