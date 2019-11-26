<template>
  <v-dialog v-model="dialog" persistent max-width="290" class="text-xs-center">
    <v-time-picker v-model="picker">
      <v-btn class="primary" flat @click="save">Accept</v-btn>
      <v-btn class="error" flat @click="$emit('close')">Cancel</v-btn>
    </v-time-picker>
  </v-dialog>
</template>

<script>
export default {
  name: "TimePickerDiag",
  props: {
    dialog: Boolean,
    selectedOrder: Object
  },
  data() {
    return {
      picker: null
    };
  },
  methods: {
    save:function(){
      var data = {order:this.selectedOrder, picker:this.picker}
      this.$emit('save',data)
    }
  }
};
</script>
