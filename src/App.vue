<template>
  <DatePicker v-model="date" range :format="format" selectText="Добавить" cancelText="" locale="ru-RU" month/>
</template>

<script>
import { ref } from 'vue';
export default {
  setup() {

    const date = ref(new Date());
    // In case of a range picker, you'll receive [Date, Date]
    const format = (dates) => {
      const datesArr = []
      dates.map(date => {
        const day = date.getDate();
        const month = date.getMonth() + 1;
        const year = date.getFullYear();
        datesArr.push(`${day}.${month}.${year}`)
      })
      return `${datesArr[0]}-${datesArr[1]}`
    }

    return {
      date,
      format,

    }
  },
  name: 'App',
  components: {

  },
  // data(){
  //   return{
  //
  //
  //   }
  // },
  methods:{
    // dateCalc(){
      // const startDate = new Date();
      // const endDate = new Date(new Date().setDate(startDate.getDate() + 7));
      // this.date = [startDate, endDate];


    //}
  },
  mounted() {
    //this.dateCalc()
  }
}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
#app{
  background-color: cornflowerblue;
  height: 100vh;
  width: 100vw;
}
.dp__input_wrap{
  width: 250px!important;
  margin: 0 auto;
}
</style>
