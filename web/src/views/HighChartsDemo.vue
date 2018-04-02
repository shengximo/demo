<template>
  <div class="animated fadeIn">
    <b-card-group columns class="card-columns cols-2">
      <b-card header="Pie Chart">
        <div class="chart-wrapper">
          <pie-chart/>
        </div>
      </b-card>
      <b-card header="Bar Chart">
        <div class="chart-wrapper">
          <bar-chart :title = "bar" :series = "barSeries"></bar-chart>
        </div>
      </b-card>
      <b-card header="Bar Chart">
        <div class="chart-wrapper">
          <d-line-chart :title = "dline" :series = "dlineSeries"></d-line-chart>
        </div>
      </b-card>
    </b-card-group>
  </div>
</template>
<script>
import PieChart from './highcharts/PieChart'
import BarChart from './highcharts/BarChart'
import DLineChart from './highcharts/DLineChart'
// import dlineoptions from './highcharts/dlineoptions'
// import baroptions from './highcharts/baroptions'
export default {
  name: 'hightchartsdemo',
  components: {
    PieChart,
    BarChart,
    DLineChart
  },
  data () {
    return {
      bar: 'Test The Bar Chart!',
      barSeries: [{
        name: 'Year 2800',
        data: [107, 31, 635, 203, 2]
      }, {
        name: 'Year 3900',
        data: [133, 156, 947, 408, 6]
      }, {
        name: 'Year 4012',
        data: [1052, 954, 4250, 740, 38]
      }],
      dline: 'Test the Dynamic Line Chart!',
      dlineSeries: [{
        name: 'Random data',
        data: (function () {
          // generate an array of random data
          var data = []
          var time = (new Date()).getTime()
          var i
          for (i = -19; i <= 0; i += 1) {
            data.push({
              x: time + i * 1000,
              y: Math.random()
            })
          }
          return data
        }())
      }]
    }
  }
}
</script>

//for example soure code for tempoary using

