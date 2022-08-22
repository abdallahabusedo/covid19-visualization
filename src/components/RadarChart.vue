<template>
      <canvas  aria-label="Hello ARIA World" role="img" id="myChart3"></canvas>
</template>

<script>
import Chart from "chart.js/auto"

export default {
    props: ['DeathsToltals','PositiveCasestotals',"RecoverdToltals"],
    mounted(){
        const ctx = document.getElementById("myChart3")
        const data = {
            labels: [
                'PositiveCasestotals',
                'RecoverdToltals',
                'DeathsToltals'
            ],
            datasets: [{
                label: 'all numbers in the first day',
                data: [this.PositiveCasestotals[0],this.RecoverdToltals[0],this.DeathsToltals[0]],
                fill: true,
                backgroundColor: 'rgba(255, 99, 132, 0.2)',
                borderColor: 'rgb(255, 99, 132)',
                pointBackgroundColor: 'rgb(255, 99, 132)',
                pointBorderColor: '#fff',
                pointHoverBackgroundColor: '#fff',
                pointHoverBorderColor: 'rgb(255, 99, 132)',
                hoverOffset: 20
            },{
                label: 'all numbers in the first day',
                data: [this.PositiveCasestotals[100],this.RecoverdToltals[100],this.DeathsToltals[100]],
                fill: true,
                backgroundColor: 'rgba(54, 162, 235, 0.2)',
                borderColor: 'rgb(54, 162, 235)',
                pointBackgroundColor: 'rgb(54, 162, 235)',
                pointBorderColor: '#fff',
                pointHoverBackgroundColor: '#fff',
                pointHoverBorderColor: 'rgb(54, 162, 235)',
                hoverOffset: 20
            }
            ]
            };
        const myChart = new Chart(ctx, {  
            type: 'radar',
            data: data,
            options: {
                elements: {
                line: {
                    borderWidth: 4
                }
                },
                responsive: true,   
            },
        });
    myChart
    }
}
</script>

<style>

</style>