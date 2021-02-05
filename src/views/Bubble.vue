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
  return Math.round(Math.random() * 100);
};

export default {
    components: {

    },
    data() {
      return {
        chartData: {
          datasets: [{
            label: 'My First dataset',
            backgroundColor: 'rgba(255,0,0,0.3)',
            borderColor: 'rgba(255,0,0,0.8)',
            borderWidth: 1,
            data: [{
              x: randomScalingFactor(),
              y: randomScalingFactor(),
              r: Math.abs(randomScalingFactor()) / 5,
            }, {
              x: randomScalingFactor(),
              y: randomScalingFactor(),
              r: Math.abs(randomScalingFactor()) / 5,
            }, {
              x: randomScalingFactor(),
              y: randomScalingFactor(),
              r: Math.abs(randomScalingFactor()) / 5,
            }, {
              x: randomScalingFactor(),
              y: randomScalingFactor(),
              r: Math.abs(randomScalingFactor()) / 5,
            }, {
              x: randomScalingFactor(),
              y: randomScalingFactor(),
              r: Math.abs(randomScalingFactor()) / 5,
            }, {
              x: randomScalingFactor(),
              y: randomScalingFactor(),
              r: Math.abs(randomScalingFactor()) / 5,
            }, {
              x: randomScalingFactor(),
              y: randomScalingFactor(),
              r: Math.abs(randomScalingFactor()) / 5,
            }]
          }, {
            label: 'My Second dataset',
            backgroundColor: 'rgba(2205,186,150,0.3)',
            borderColor: 'rgba(2205,186,150,0.8)',
            borderWidth: 1,
            data: [{
              x: randomScalingFactor(),
              y: randomScalingFactor(),
              r: Math.abs(randomScalingFactor()) / 5,
            }, {
              x: randomScalingFactor(),
              y: randomScalingFactor(),
              r: Math.abs(randomScalingFactor()) / 5,
            }, {
              x: randomScalingFactor(),
              y: randomScalingFactor(),
              r: Math.abs(randomScalingFactor()) / 5,
            }, {
              x: randomScalingFactor(),
              y: randomScalingFactor(),
              r: Math.abs(randomScalingFactor()) / 5,
            }, {
              x: randomScalingFactor(),
              y: randomScalingFactor(),
              r: Math.abs(randomScalingFactor()) / 5,
            }, {
              x: randomScalingFactor(),
              y: randomScalingFactor(),
              r: Math.abs(randomScalingFactor()) / 5,
            }, {
              x: randomScalingFactor(),
              y: randomScalingFactor(),
              r: Math.abs(randomScalingFactor()) / 5,
            }]
          }]
        }
      }
    },
    mounted() {
      var canv = document.getElementById("chart-area");

      var ploar = new Chart(canv, {
        type: 'bubble',
        data: this.chartData,
        options: {
          responsive: true,
          plugins: {
            title: {
              display: true,
              text: 'Chart.js Bubble Chart'
            },
            tooltip: {
              mode: 'point'
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