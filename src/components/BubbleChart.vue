<template>
  <h3>all numbers in the first day</h3>
  <div width="50px" height="50px" >
      <canvas  aria-label="Hello ARIA World" role="img" id="myChart4"></canvas>
  </div>
</template>

<script>
import Chart from "chart.js/auto"

export default {
    props: ['DeathsToltals','PositiveCasestotals',"RecoverdToltals"],
    mounted(){
        const ctx = document.getElementById("myChart4")
        const data = {
            labels: [
                'PositiveCasestotals',
                'RecoverdToltals',
                'DeathsToltals'
            ],
            datasets: [{
                label: 'all numbers in the first day',
                data: [{
                    x:this.PositiveCasestotals[0],
                    y:this.RecoverdToltals[0],
                    z:this.DeathsToltals[0]
                    },{
                    x:this.PositiveCasestotals[1],
                    y:this.RecoverdToltals[1],
                    z:this.DeathsToltals[1]
                    },{
                    x:this.PositiveCasestotals[2],
                    y:this.RecoverdToltals[2],
                    z:this.DeathsToltals[2]
                    },{
                    x:this.PositiveCasestotals[3],
                    y:this.RecoverdToltals[3],
                    z:this.DeathsToltals[3]
                    },{
                    x:this.PositiveCasestotals[4],
                    y:this.RecoverdToltals[4],
                    z:this.DeathsToltals[4]
                    },{
                    x:this.PositiveCasestotals[5],
                    y:this.RecoverdToltals[5],
                    z:this.DeathsToltals[5]
                    }
                ],
                backgroundColor: 'rgb(255, 99, 132)',
                hoverOffset: 20
            }]
            };
        const myChart = new Chart(ctx, {  
            type: 'bubble',
            data: data,
            options: {
                responsive: true,
            }
        });
    myChart
    }
}
</script>

<style>

</style>