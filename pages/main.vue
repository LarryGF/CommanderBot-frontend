
<template>
  <v-layout column justify-center align-center>
            <TimePickerDiag :dialog="dialog" :selectedOrder="selectedOrder" @close="dialog=false" @save="setTime"/>
    <v-flex xs12 sm8 md6>
      <v-btn color="primary" right bottom fixed icon fab @click="addOrder">
        <v-icon>add</v-icon>
      </v-btn>
      <div class="text-xs-center">
        <v-avatar class="my-4" size="150">
          <img src="/v.png" alt="Vuetify.js" class="mb-5">
        </v-avatar>
      </div>
      <v-card width="1000">
        <v-toolbar dark>
          <v-card-title class="headline">Define the orders for each group</v-card-title>
          <v-spacer></v-spacer>
        </v-toolbar>
        <v-card-text>
          <v-layout column v-for="order in orders" :key="order.id">
            
            <v-layout row justify-space-around class="mt-3">
              <v-avatar color="blue" class="mt-2 mx-3">
                <h3 style="color:white">{{order.id}}</h3>
              </v-avatar>

              <v-autocomplete outline v-model="order.group" dense label="Groups" class="mx-1" ></v-autocomplete>
              <v-flex xs2>
                <v-autocomplete outline v-model="order.target" dense label="Target" class="mx-1"></v-autocomplete>
              </v-flex>
              <v-flex xs3>
                <v-text-field outline label="Additional text" v-model="order.text" class="mx-1"></v-text-field>
              </v-flex>
              <v-btn icon color="blue" large class="mt-2">
                <v-icon color="white" @click.stop="setDialog()">alarm_add</v-icon>
              </v-btn>
              <blockquote class="mt-4 mx-2">{{order.time}}</blockquote>
            </v-layout>
            <v-divider class="mb-2"></v-divider>
          </v-layout>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import TimePickerDiag from "../components/TimePicker.vue";
export default {
  data() {
    return {
      count: 0,
      picker:null,
      dialog: false,
      orders: [
        {
          id: 0,
          groups: [],
          target: "",
          text: "",
          time: "00:00"
        }
      ],
      selectedOrder:null
    };
  },
  components: {
    TimePickerDiag
  },
  methods: {
    addOrder: function() {
      this.count++;
      console.log(this.count);
      this.orders.push({
        id: this.count,
        groups: [],
        target: "",
        text: "",
        time: "00:00"
      });
    },
    setTime: function(data) {
      console.log(data);
      this.dialog = false
      var index = this.orders.indexOf(data.order)
      this.orders[index].time = data.picker
      // this.order.time = data
      // this.dialog = false
    },
    setDialog: function(order){
      console.log('er')
      this.selectedOrder=order
      this.dialog = true

    }
  }
};
</script>