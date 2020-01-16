<template lang="html">
  <div>
    <select v-model="selectedCountry" v-on:change="handleChange">
      <option v-for="(country, index) in countries" :key="index" :value="country">{{ country.name }}</option>
    </select>
  </div>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'country-select',
  data() {
    return {
      selectedCountry: {}
    }
  },
  props: ['countries'],
  methods: {
    handleChange() {
      eventBus.$emit('country-selected', this.selectedCountry);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
