<template>
  <article v-if="munro">
      <!-- <h3>{{ country.name }}</h3>
      <dl>
        <dt>Height (metres):</dt>
        <dd>{{ country.height }}m</dd>

        <dt>Region:</dt>
        <dd>{{ country.region }}</dd>

        <dt>Meaning:</dt>
        <dd>{{ country.meaning }}</dd>
      </dl> -->
    </article>
</template>

<script>
export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>
