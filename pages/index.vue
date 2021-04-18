<template>
  <div class="v-main">
    <v-row>
      <v-col
        cols="12"
        sm="2"
      >
        <v-sheet
          rounded="lg"
          min-height="268"
        >
        </v-sheet>
      </v-col>

      <v-col
        cols="12"
        sm="8"
      >
        <v-sheet
          min-height="70vh"
          rounded="lg"
        >
        </v-sheet>
      </v-col>

      <v-col
        cols="12"
        sm="2"
      >
        <v-sheet
          rounded="lg"
          min-height="268"
        >
        </v-sheet>
      </v-col>
    </v-row>
  </div>
</template>

<script>

export default {
  layout: 'layoutAlumni'
}
</script>

<style scoped>
.v-main {
  margin-top: 90px;
  margin-bottom: 30px;
}
</style>
