<template>
  <div class="animated fadeIn">
    <b-card-group columns class="card-columns cols-2">
      <b-card header="Pie Chart">
        <div class="chart-wrapper">
          <high-pie-example :id="id" :option="option"></high-pie-example>
        </div>
      </b-card>
    </b-card-group>
  </div>
</template>
<script>
import HighPieExample from './highcharts/HighPieExample'
import highpieopions from './highcharts-options/pieoptions'
export default {
  name: 'hightcharts',
  data () {
    let option = highpieopions.pie
    return {
      id: 'test',
      option: option
    }
  },
  components: {
    HighPieExample
  }
}
</script>

//for example soure code for tempoary using
