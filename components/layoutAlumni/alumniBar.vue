<template>
  <div>
    <!--  Bar logo  -->
    <v-app-bar
      color="white"
      class="light-blue lighten-5 hidden-sm-and-down"
      flat
      app
    >
      <v-container>
        <v-row dense>
          <v-avatar
            class="mr-3"
            color="grey darken-1 shrink"
            size="50"
          >
            <img
              src="~/static/logo.png"
              alt="John"
            >
          </v-avatar>
          <div class="font-weight-black">
            <div>สมาคมศิษย์เก่าพณิชยการพระนคร</div>
            <div>THE ASSOCIATION OF BANGKOK COMMERCIAL ALUMNI</div>
          </div>
        </v-row>
      </v-container>
    </v-app-bar>
    <!--  Bar logo  -->

    <!--  Bar menu  -->
    <v-app-bar
      :style="{top:toolbarHeight + 'px'}"
      color="white"
      class="light-blue lighten-2"
      flat
      app
    >
      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-avatar
            class="hidden-md-and-up"
            color="grey darken-1 shrink"
            size="40"
          >
            <img
              src="https://cdn.vuetifyjs.com/images/john.jpg"
              alt="John"
            >
          </v-avatar>
        </template>
        <v-list>
          <v-list-item
            v-for="(item, index) in items"
            :key="index"
          >
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>

      <v-tabs
        centered
        class="ml-n9"
        color="grey lighten-5"
      >
        <v-tab
          v-for="link in links"
          :key="link"
          class="white--text"
        >
          {{ link }}
        </v-tab>
      </v-tabs>

      <v-menu
        rounded="lg"
        offset-y
      >
        <template v-slot:activator="{ on, attrs }">
          <v-avatar
            class="hidden-sm-and-down"
            color="grey darken-1 shrink"
            size="40"
            v-bind="attrs"
            v-on="on"
          >
            <img
              src="https://cdn.vuetifyjs.com/images/john.jpg"
              alt="John"
            >
          </v-avatar>
        </template>
        <v-list>
          <v-list-item
            v-for="(item,i) in items"
            :key="i"
            link
          >
            <v-list-item-title v-text="item.title"></v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
    <!--  Bar menu  -->
  </div>
</template>

<script>
export default {
  name: 'alumniBar',
  data() {
    return {
      icons: [
        'mdi-facebook',
        'mdi-twitter',
        'mdi-linkedin',
        'mdi-instagram'
      ],
      items: [
        { title: 'Profile' },
        { title: 'จัดการกระทู้' },
        { title: 'ออกจากระบบ' }
      ],
      links: [
        'หน้าหลัก',
        'ข่าว',
        'ประวัติ',
        'พณิชยการพระนคร',
        'วัตถุมงคล',
        'อัลบั้มภาพ',
        'เพลง พ.พ.',
        'พูดคุย',
        'ติดต่อเรา',
        'รุ่น พ.พ.'
      ]
    }
  },
  computed: {
    toolbarHeight() {
      if (this.$vuetify.breakpoint.xs || this.$vuetify.breakpoint.sm) {
        return 0
      }

      return this.$vuetify.application.top
    }
  }
}
</script>

<style scoped>

</style>
