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
import AlumniBar from '~/components/layoutAlumni/alumniBar'
import AlumniFooter from '~/components/layoutAlumni/alumniFooter'

export default {
  name: 'layoutAlumni',
  components: { AlumniFooter, AlumniBar },
  data() {
    return {}
  }
}
</script>

<style scoped>
</style>
