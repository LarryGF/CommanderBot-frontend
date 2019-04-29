<template>
  <v-layout justify-center>
      <v-flex  xs6 column class="mt-5">
    <h2 class="text-xs-center">Go to CommanderBot and /generate_auth, 
      copy the resulting hash and paste it here.</h2>
     <v-text-field outline class="mt-4"></v-text-field>
     <v-layout row justify-end>

     <v-btn class="primary text-xs-center" @click="$router.replace('/main')">Submit</v-btn>
     </v-layout>
      </v-flex>
  </v-layout>
</template>

<script>
  export default {
    layout:"login",
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