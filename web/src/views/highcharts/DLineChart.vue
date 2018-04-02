<template>
  <div>
  </div>
</template>

<script>
  import Highcharts from 'highcharts'
  export default {
    name: 'DLineChart',
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
            type: 'spline',
            animation: Highcharts.svg, // don't animate in old IE
            marginRight: 10,
            events: {
              load: function () {
                // set up the updating of the chart each second
                var series = this.series[0]
                setInterval(function () {
                  var x = (new Date()).getTime() // current time
                  var y = Math.random()
                  series.addPoint([x, y], true, true)
                }, 1000)
              }
            }
          },
          title: {
            text: this.title
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
