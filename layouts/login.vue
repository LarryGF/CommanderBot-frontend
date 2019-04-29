<template>
  <v-app >
    
    <v-toolbar fixed app :clipped-left="clipped" dark>
      <v-spacer></v-spacer>
      <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>
    <v-content>
      <v-container fill-height>
        <nuxt />
      </v-container>
    </v-content>
    
    <v-footer :fixed="fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        clipped: false,
        drawer: true,
        fixed: false,
        items: [
          { icon: 'apps', title: 'Main', to: '/' },
          { icon: 'settings', title: 'Settings', to: '/settings' }
        ],
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'CommanderBot'
      }
    }
  }
</script>
