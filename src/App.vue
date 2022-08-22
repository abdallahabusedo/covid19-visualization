<template>
<div id="app" class="container">
  <div class="row mt-5" v-if="PositiveCases.length > 0">
    <div class="col">
      <h2>Positives</h2>
      <BarChart :dates="dates" :totals="PositiveCasestotals" />
      <LinesChart :dates="dates" :totals="PositiveCasestotals" />
      <AreaChart 
      :PositiveCasestotals="PositiveCasestotals"
      :DeathsToltals="DeathsToltals"
      :RecoverdToltals="RecoverdToltals"
      />
    </div>
  </div>
  
 
</div>
</template>

<script>
import axios from "axios"
import moment from 'moment'
import BarChart from "./components/BarChart.vue"
import LinesChart from "./components/LinesChart.vue"
import AreaChart from "./components/AreaChart.vue"

export default {
  name: 'App',
  components: {
    BarChart,
    LinesChart,
    AreaChart
},
  data(){
    return{
      PositiveCases : [],
      Deaths: [],
      Recoverd: [],
      dates: [],
      PositiveCasestotals: [],
      DeathsToltals: [],
      RecoverdToltals: [],
    }
  },
  async created(){
    const {data} = await axios.get('https://api.covid19api.com/live/country/egypt')
    data.forEach(d => {
      const date = moment(d.Date,"YYYYMMDD").format("YYYY/MM/DD")
      const {Confirmed,Deaths,Recovered} = d
      this.PositiveCases.push({date, total : Confirmed})
      this.Deaths.push({date, total : Deaths})
      this.Recoverd.push({date, total : Recovered})
      this.dates = this.PositiveCases.map(d => d.date)
      this.PositiveCasestotals = this.PositiveCases.map(d => d.total)
      this.DeathsToltals = this.Deaths.map(d => d.total)
      this.RecoverdToltals = this.Recoverd.map(d => d.total)
      // console.log("PositiveCases",this.PositiveCases);
      // console.log("Deaths",this.Deaths);
      // console.log("Recoverd",this.Recoverd);
    
    });
  }
}
</script>

<style>
body{
  margin : 0;
  padding: 0;
}
h3{
  margin-top : 50px;
}
</style>
