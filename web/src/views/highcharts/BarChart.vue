<template>
  <div> {{ "title" }}
  </div>
</template>

<script>
  import Highcharts from 'highcharts'
  export default {
    name: 'BarChart',
    props: {
      title: String,
      series: Array
    },
    data: function () {
      return {
        target: undefined
      }
    },
    mounted () {
      this.target = Highcharts.chart(this.$el,
        {
          chart: {
            type: 'bar'
          },
          title: {
            text: this.title
          },
          subtitle: {
            text: 'Source: <a href="https://en.wikipedia.org/wiki/World_population">Wikipedia.org</a>'
          },
          xAxis: {
            categories: ['Africa', 'America', 'Asia', 'Europe', 'Oceania'],
            title: {
              text: null
            }
          },
          yAxis: {
            min: 0,
            title: {
              text: 'Population (millions)',
              align: 'high'
            },
            labels: {
              overflow: 'justify'
            }
          },
          tooltip: {
            valueSuffix: ' millions'
          },
          plotOptions: {
            bar: {
              dataLabels: {
                enabled: true
              }
            }
          },
          legend: {
            layout: 'vertical',
            align: 'right',
            verticalAlign: 'top',
            x: -40,
            y: 80,
            floating: true,
            borderWidth: 1,
            shadow: true
          },
          credits: {
            enabled: false
          },
          series: this.series
        }
      )
    },

    beforeDestroy: function () {
      this.target.destroy()
    }

  }
</script>
