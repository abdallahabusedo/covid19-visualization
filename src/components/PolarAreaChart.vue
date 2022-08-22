<template>
  <h3>Polar Area Chart</h3>
  <div width="50px" height="50px">
      <canvas  aria-label="Hello ARIA World" role="img" id="myChart2"></canvas>
  </div>
</template>

<script>
import Chart from "chart.js/auto"

export default {
    props: ['DeathsToltals','PositiveCasestotals',"RecoverdToltals"],
    mounted(){
        const ctx = document.getElementById("myChart2")
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
            type: 'polarArea',
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