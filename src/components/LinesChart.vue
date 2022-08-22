<template>
    <h3>Line Chart</h3>
    <Line :chart-data="chartData" :chart-options="chartOptions" />
</template>

<script>
import {Line} from 'vue-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale,LineController, LineElement, PointElement } from 'chart.js'
ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale,LineController, LineElement, PointElement)

export default {
props: ['dates','totals'],
components: {Line},
data(props){
    return {
        chartData:{ 
            labels:props.dates,
            datasets:[
            {
                label: "Positives",
                backgroundColor: 'red',
                data:props.totals
            }
            ],
        },
        chartOptions: {
            responsive: true,
            maintainAspectRatio: false
      }
    }
}
}
</script>

<style>

</style>