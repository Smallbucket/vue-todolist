<template>
  <div class="small">
    <div style="width:80%">  
      <canvas id="chart-area"></canvas>
    </div>
  </div>
</template>
<script>
import Chart from 'chart.js';

function randomScalingFactor() {
  return Math.round(Math.random() * 1000);
};

const colorNames = [
]

export default {
    components: {

    },
    data() {
      return {
        chartData: {
          labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
          datasets: [{
            type: 'line',
            label: 'Dataset 1',
            borderColor: 'rgba(0,205,0,0.3)',
            borderWidth: 2,
            fill: false,
            data: [
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor()
            ]
          }, {
            type: 'bar',
            label: 'Dataset 2',
            backgroundColor: 'rgba(255,0,0,0.3)',
            data: [
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor()
            ],
            borderColor: 'white',
            borderWidth: 2
          }, {
            type: 'bar',
            label: 'Dataset 3',
            backgroundColor: 'rgba(205,186,150,0.3)',
            data: [
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor(),
              randomScalingFactor()
            ]
          }]
        }
      }
    },
    mounted() {
      var canv = document.getElementById("chart-area");

      var ploar = new Chart(canv, {
        type: 'bar',
        data: this.chartData,
        options: {
          responsive: true,
          plugins: {
            title: {
              display: true,
              text: 'Chart.js Combo Bar Line Chart'
            },
            tooltip: {
              mode: 'index',
              intersect: true
            }
          }
        }
      });
    },
    methods: {

    }
}
</script>

<style>
canvas {
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none; 
}

button {
  margin-top: 20px;
  margin-left: 20px;
}
</style>