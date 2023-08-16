<template>
  <header>
    <h1>Income Tracker</h1>
    <h2>Total: ${{ totalIncome }}</h2>
  </header>
</template>

<script>
export default {
  props: {
    totalIncome: Number
  }
}
</script>

<style scoped>

header{
  height: 100px;
  width: 100%;
  background: #b1b1b1;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 4rem;
}


</style>

