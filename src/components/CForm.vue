<template>
  <form @submit.prevent="FormHandler">
    <input type="text" placeholder="Decription..." v-model="FormData.desc">
    <input type="number" placeholder="Value..." v-model="FormData.value">
    <input type="date" placeholder="Date" v-model="FormData.date">
    <input type="submit" placeholder="submit">
  </form>
</template>

<script>

import { reactive } from "vue";

export default {
  props: {
    state: Object
  },
  setup(props, { emit }){
    
      const FormData = reactive({
        desc: null,
        value: null,
        date: null
      });

      function FormHandler(){

          emit('add-income', {
            desc: FormData.desc,
            value: FormData.value,
            date: FormData.date,
          });

          FormData.desc = null;
          FormData.value = null;
          FormData.date = null;

      }

      return{
        FormHandler,
        FormData,
      }

  }

}
</script>

<style>

</style>