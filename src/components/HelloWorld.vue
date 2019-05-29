<template>
  <section class="section">
    <div class="container">
      <h1 class="title">
        Bulma in Vue-CLI
      </h1>

      <div class="columns is-tablet">
        <card v-for="i in 4" :key="i" :num="i"></card>
      </div>
    </div>
  </section>
</template>

<script>
import Card from './Card'
export default {
  components: {
    Card
  }
}
</script>

<style lang="scss" scoped>
</style>