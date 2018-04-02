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
  import CloudVMTree from './ztrees/CloudVMTree'
  // import BarChart from './highcharts/BarChart'

  export default {
    name: 'ztreesdemo',
    components: {
      CloudVMTree
    },
    data () {
      return {

      }
    }
  }
</script>


