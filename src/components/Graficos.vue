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
            backgroundColor: ['#88b257', '#4a701c', '#486623', '#284703', '#434d36'], // Cores das barras
            data: [30, 45, 100, 70, 65] // Seus dados
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
  <div class="grafico-container">
    <div class="grafico">
      <Bar
        id="my-chart-id"
        :options="chartOptions"
        :data="chartData"
      />
    </div>
  </div>
</template>

<style scoped>
.grafico-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh; /* Isso fará com que o container ocupe toda a altura da viewport */
}

.grafico {
  width: 500px; 
  height: 300px;
}
</style>