<template>
  <h3>Area Chart</h3>
  <div width="100px" height="50px">

      <canvas  aria-label="Hello ARIA World" role="img" id="myChart"></canvas>
  </div>
</template>

<script>
import Chart from "chart.js/auto"

export default {
    props: ['DeathsToltals','PositiveCasestotals',"RecoverdToltals"],
    mounted(){
        const ctx = document.getElementById("myChart")
        const data = {
            labels: [
                'PositiveCasestotals',
                'RecoverdToltals',
                'DeathsToltals'
            ],
            datasets: [{
                label: 'all numbers in the first day',
                data: [this.PositiveCasestotals[0],this.RecoverdToltals[0],this.DeathsToltals[0]],
                backgroundColor: [
                'rgb(255, 99, 132)',
                'rgb(54, 162, 235)',
                'rgb(255, 205, 86)'
                ],
                hoverOffset: 20
            }]
            };
        const myChart = new Chart(ctx, {  
            type: 'doughnut',
            data: data,
            options: {
                responsive: true,
                maintainAspectRatio: false
            }
        });
    myChart
    }
}
</script>

<style>

</style>