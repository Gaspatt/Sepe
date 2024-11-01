<script>
import { Bar } from 'vue-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

export default {
  name: 'BarChart',
  components: { Bar },
  data() {
    return {
      chartData: {
        labels: ['Janeiro', 'Fevereiro', 'Março', 'Abril', 'Maio'], // Seus rótulos
        datasets: [
          {
            label: 'Dados do Gráfico',
            backgroundColor: ['#f87979', '#7979f8', '#79f879', '#f8f879', '#f879f8'], // Cores das barras
            data: [40, 20, 12, 30, 25] // Seus dados
          }
        ]
      },
      chartOptions: {
        responsive: true,
        plugins: {
          legend: {
            display: true
          },
          title: {
            display: true,
            text: 'Meu Gráfico de Barras'
          }
        }
      }
    }
  }
}

</script>

<template>
  <div style="width: 500px; height: 300px;">
    <Bar
      id="my-chart-id"
      :options="chartOptions"
      :data="chartData"
    />
  </div>
</template>