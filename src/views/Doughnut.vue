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
        datasets: [{
          data: [
            randomScalingFactor(),
            randomScalingFactor(),
            randomScalingFactor(),
            randomScalingFactor(),
            randomScalingFactor(),
          ],
          backgroundColor: [
            'rgba(255,0,0,0.3)',
            'rgba(2205,186,150,0.3)',
            'rgba(238,173,14,0.3)',
            'rgba(238,238,0,0.3)',
            'rgba(0,205,0,0.3)',
          ],
          label: 'My dataset' // for legend
        }],
        labels: [
          'Red',
          'Orange',
          'Yellow',
          'Green',
          'Blue'
        ]
      }
    },
    mounted() {
      var canv = document.getElementById("chart-area");

      var ploar = new Chart(canv, {
        type: 'doughnut',
        data: {
          datasets: this.datasets,
          labels: this.labels
        },
        options: {
          responsive: true
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