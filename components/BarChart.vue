<script>
import { Line } from 'vue-chartjs'
export default {
  extends: Line,
  data(){
    return {
        chartdata: {
            labels: ['January', 'February'],
            datasets: [
                {
                label: ['Data One'],
                backgroundColor: '#f87979',
                data: [50, 40]
                }
            ]
        },
        options: {
            responsive: true,
            maintainAspectRatio: false
        }
    }
  },
  mounted () {
    this.renderChart(this.chartdata, this.options)
  }
}
</script>
