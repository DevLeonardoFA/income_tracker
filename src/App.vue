
<template>
  <CHeader :totalIncome="state.TotalIncome" />
  <CForm @add-income="addincome" />
  <CList :state="state" />
</template>

<script>
import { reactive, computed } from 'vue';
import CHeader from './components/CHeader';
import CForm from './components/CForm';
import CList from './components/CList.vue';

export default {
 /* eslint-disable */ 
  
  components: { 
    CHeader,
    CForm,
    CList
  },

  setup() {

    const state = reactive({

      income: [],

      TotalIncome: computed(() => {
        let temp = 0;

        if (state.income.length > 0) {
          for (let i = 0; i < state.income.length; i++) {
            temp += state.income[i].value;
          }
        }

        return temp;
      }),

      sortedIncome: computed(() => {

        let temp = [];

        temp = state.income.sort(function(a, b){
          return b.date = a.date
        });

        return temp;

      })

    });

    function addincome(data){

      state.income = [...state.income, {
        id: Date.now(),
        desc: data.desc,
        value: data.value,
        date: data.date
      }]

    }

    

    return { state,addincome };

  }
};

</script>

<style>

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body{
  background: #e0e0e0;
}

</style>
