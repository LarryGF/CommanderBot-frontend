
<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <div class="text-xs-center">
        <v-avatar class="my-4" size="150">

        <img src="/v.png" alt="Vuetify.js" class="mb-5" />
        </v-avatar>
      </div>
      <v-card  width="1000">
        <v-toolbar dark>

        <v-card-title class="headline">Define the orders for each group</v-card-title>
        </v-toolbar>
        <v-card-text>
         <template>
           <v-layout row justify-space-around>
             <v-avatar color="blue" class="mt-2 mx-3">
               <h3 style="color:white">1</h3>
             </v-avatar>

             <v-autocomplete outline 
             dense
             label="Groups" class="mx-1"></v-autocomplete>
             <v-flex xs2>

             <v-autocomplete outline
             dense
             label="Target" class="mx-1"></v-autocomplete>
             </v-flex>
              <v-flex xs3>

             <v-text-field outline
             label="Additional text" class="mx-1"></v-text-field>
             </v-flex>
             <v-btn icon color="blue" large class="mt-2"><v-icon color="white">alarm_add</v-icon></v-btn>
             <blockquote class="mt-3 mx-2">time</blockquote>
           </v-layout>
           <v-divider class="my-2"></v-divider>
         </template>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="primary" flat nuxt to="/inspire">Continue</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  export default {
    data () {
      return {
       
      }
    }
  }
</script>