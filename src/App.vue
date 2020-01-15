<template>
  <div id="app">
    <h1>Countries</h1>
    <country-select></country-select>
  </div>
</template>

<script>
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
    // .then(munros => this.munros = munros)
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
