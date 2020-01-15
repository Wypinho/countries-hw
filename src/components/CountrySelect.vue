<template lang="html">
  <div>
    <select>
      <option v-for="country in countries">{{ country.name }}</option>

      <!-- <list-item v-for="(munro, index) in munros" :munro="munro" :key="index"></list-item> -->
    </select>
  </div>
</template>

<script>
export default {
  name: 'country-select',
  props: ['countries']
}
</script>

<style lang="css" scoped>
</style>
