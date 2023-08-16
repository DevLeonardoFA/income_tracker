<template>
    <div class="income_item">
        <div class="close" @click="RemoveIncome">X</div>
        <div class="desc">{{ income.desc }}</div>
        <div class="value">{{ income.value }}</div>
        <div class="date">{{ f_date }}</div>
    </div>
</template>

<script>
export default {
    props: {
        income: Object
    },
    setup(props){
        let date = new Date(props.income.date);
        let day = date.getDate();
        let month = date.getMonth();
        let year = date.getFullYear();

        month += 1;

        day = day < 10 ? '0' + day : day;
        month = month < 10 ? '0' + month : month;

        let f_date = day + "/" + month + "/" + year;

        return{
            f_date
        }
    }
}
</script>

<style>

</style>