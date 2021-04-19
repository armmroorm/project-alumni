<template>
  <v-app id="inspire">
    <alumni-bar></alumni-bar>
    <v-main class="grey lighten-4">
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <alumni-footer></alumni-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {}
  }
}
</script>

<style scoped>
</style>
