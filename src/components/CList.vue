<template>
  <div class="income-list">
    <CItem v-for="data in state.sortedIncome" :key="data.id" :income="data" />
  </div>
</template>

<script>
import CItem from './CItem.vue'

export default {
    props: {
        state: Object
    },

    components: { 
        CItem,
    },

}
</script>

<style>

</style>