<template>
  <v-app dark>
    <v-app-bar
      :clipped-left="clipped"
      color="indigo darken-2"
      class="white--text"
      elevation="0"
      app
    >
      <v-toolbar-title class="ml-5"
        ><i class="fas fa-calculator"></i> {{ title }}</v-toolbar-title
      >
      <!-- <v-spacer></v-spacer> -->
      <v-toolbar-items class="ml-5">
        <v-btn
          v-for="item in items"
          :key="item.id"
          :to="item.to"
          class="white--text"
          text
          >{{ item.title }}</v-btn
        >
      </v-toolbar-items>
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          title: 'Calculator',
          to: '/'
        },
        {
          title: 'About',
          to: '/about'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'MFI Calculator'
    }
  }
}
</script>

<style scoped></style>
