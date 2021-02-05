<template>
  <div class="small">
    <div style="width:80%">  
      <canvas id="canvas"></canvas>
    </div>
    <button id="randomizeData">Randomize Data</button>
    <button id="addDataset">Add Dataset</button>
    <button id="removeDataset">Remove Dataset</button>         
    <button id="addData">Add Data</button>                     
    <button id="removeData">Remove Data</button>
  </div>
</template>
<script>
import Chart from 'chart.js';

function randomScalingFactor() {
  return Math.round(Math.random() * 1000);
};

export default {
    components: {

    },
    data() {
        return {

        }
    },
    mounted() {
      var canv = document.getElementById("canvas");

      var color = Chart.helpers.color;
      var radar = new Chart(canv, {
        type: 'radar',
        data: {     
          labels: [['Eating', 'Dinner'], ['Drinking', 'Water'], 'Sleeping', ['Designing', 'Graphics'], 'Coding', 'Cycling', 'Running'],
          datasets: [{
            label: 'My First dataset',
            backgroundColor: 'lavenderblush',
            borderColor: 'firebrick',
            pointBackgroundColor: 'firebrick',
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
            label: 'My Second dataset',
            backgroundColor: 'azure',
            borderColor: 'dodgerblue',
            pointBackgroundColor: 'dodgerblue',
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
        },   
        options: { 
          plugins: {
            legend: {
              position: 'top',
            },     
            title: {
              display: true,
              text: 'Chart.js Radar Chart'
            },     
          }, 
          scales: {
            r: {   
              beginAtZero: true
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
</style>