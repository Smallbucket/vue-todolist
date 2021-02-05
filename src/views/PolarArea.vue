<template>
  <div class="small">
    <div style="width:80%">  
      <canvas id="chart-area"></canvas>
    </div>
    <button @click="randomizeData">Randomize Data</button>
    <button @click="addData">Add Data</button>
    <button @click="removeData">Remove Data</button>
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
        type: 'polarArea',
        data: {
          datasets: this.datasets,
          labels: this.labels
        },
        options: {
          responsive: true,
          plugins: {
            legend: {
              position: 'right',
            },
            title: {
              display: true,
              text: 'Chart.js Polar Area Chart'
            },
          },
          scales: {
            r: {
              ticks: {
                beginAtZero: true
              },
              reverse: false
            }
          },
          animation: {
            animateRotate: false,
            animateScale: true
          }
        }
      });
    },
    methods: {
      randomizeData() {
        let _this = this
        this.datasets.forEach(function(piece, i) {
          piece.data.forEach(function(value, j) {
            value = randomScalingFactor();
          });       
        });      
      },

      addData() {
        if (this.datasets.length > 0) {
          this.labels.push('data #' + this.labels.length);
          this.datasets.forEach(function(dataset) {
            var colorName = colorNames[config.data.labels.length % colorNames.length];
            dataset.backgroundColor.push(window.chartColors[colorName]);
            dataset.data.push(randomScalingFactor());
          });
        }
      },

      removeData() {
        this.labels.pop(); // remove the label first
        this.datasets.forEach(function(dataset) {
          dataset.backgroundColor.pop();
          dataset.data.pop();
        });        
      }
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