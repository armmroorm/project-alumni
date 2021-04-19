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

    <!--  v-navigation-drawer  -->
    <v-navigation-drawer app v-model="drawer" temporary>
      <v-list-group prepend-icon="mdi-account" value="true">
        <template v-slot:activator>
          <v-list-item-content>
            <v-list-item-title>Admin</v-list-item-title>
          </v-list-item-content>
        </template>

        <v-list-item
          v-for="(menu, index) in menus"
          :key="index"
          link
          @click="logout(index)"
          :to="menu.router"
        >
          <v-list-item-icon>
            <v-icon right>{{ menu.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-title v-text="menu.title"></v-list-item-title>
        </v-list-item>
      </v-list-group>

      <v-divider light></v-divider>

      <v-list shaped>
        <v-list-item
          v-for="item in links"
          :key="item.title"
          link
          router
          :to="item.router"
        >
          <v-list-item-icon>
            <v-icon right>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!--    -->

    <!--  Bar menu  -->
    <v-app-bar
      :style="{top:toolbarHeight + 'px'}"
      color="white"
      class="light-blue lighten-2"
      flat
      app
      dark
    >
      <v-app-bar-nav-icon

        class="hidden-sm-and-up"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>

      <v-tabs
        centered
        class="ml-n9 hidden-sm-and-down"
        color="grey lighten-5"
      >
        <v-tab
          v-for="(item,i) in links"
          :key="i"
          class="white--text"
        >
          {{ item.title }}
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
            v-for="(item,i) in menus"
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
      drawer: null,
      icons: [
        'mdi-facebook',
        'mdi-twitter',
        'mdi-linkedin',
        'mdi-instagram'
      ],
      menus: [
        { title: 'Profile', icon: 'mdi-account-convert' },
        { title: 'จัดการกระทู้', icon: 'mdi-account-box', router: '' },
        { title: 'ออกจากระบบ', icon: 'mdi-logout-variant', router: '' }
      ],
      links: [
        { title: 'หน้าหลัก', icon: 'mdi-view-dashboard' },
        { title: 'ข่าว', icon: ' mdi-newspaper', router: '' },
        { title: 'ประวัติ', icon: 'mdi-star', router: '' },
        { title: 'พณิชยการพระนคร', icon: 'mdi-school', router: '' },
        { title: 'วัตถุมงคล', icon: 'mdi-star-outline', router: '' },
        { title: 'อัลบั้มภาพ', icon: 'mdi-view-grid', router: '' },
        { title: 'เพลง พ.พ.', icon: 'mdi-music-box', router: '' },
        { title: 'พูดคุย', icon: 'mdi-pencil-box', router: '' },
        { title: 'ติดต่อเรา', icon: 'mdi-book-open', router: '' },
        { title: 'รุ่น พ.พ.', icon: 'mdi-logout-variant', router: '' },
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
