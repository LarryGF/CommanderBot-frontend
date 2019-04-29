<template>
  <v-layout justify-center>
    <v-flex column xs12 sm8 md6>
      <v-card >
        <v-toolbar dark>
          <v-card-title class="headline" >Add a new Group -> Group-id pair</v-card-title>
        </v-toolbar>
        <v-card-text>
          <v-layout row>
            <v-spacer></v-spacer>
            <v-text-field outline
            label="Group"></v-text-field>
            <v-icon class="mb-4">arrow_left</v-icon>
            <v-icon class="mb-4">arrow_right</v-icon>
            <v-text-field outline
            label="Group-id"></v-text-field>
            <v-spacer></v-spacer>
          </v-layout>
        </v-card-text>
        <v-card-actions>
          <v-layout row justify-end>
          <v-btn class="error">Cancel</v-btn>
          <v-btn class="primary">Accept</v-btn>
          </v-layout>
        </v-card-actions>
      </v-card>
      
    </v-flex>
  </v-layout>
</template>
