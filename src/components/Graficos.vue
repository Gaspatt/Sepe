<script>
import { Bar } from 'vue-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'
import Footer from './FoHead/Footer.vue'
import Header from './FoHead/Header.vue'
import Planta from '@/assets/imagens/planta.webp'

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

export default {
  name: 'BarChart',
  components: { 
    Bar,
    Footer,
    Header
  },
  data() {
    return {
      chartData: {
        labels: ['Janeiro', 'Fevereiro', 'Março', 'Abril', 'Maio'],
        datasets: [
          {
            label: 'Dados do Gráfico',
            backgroundColor: ['#88b257', '#4a701c', '#486623', '#284703', '#434d36'],
            data: [30, 45, 100, 70, 65]
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
  <div class="page-container">
    <Header />
    <div class="grafico-container">
      <div class="grafico">
        <Bar
          id="my-chart-id"
          :options="chartOptions"
          :data="chartData"
        />
      </div>
    </div>

    

    <Footer />
  </div>
</template>

<style scoped>
.page-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  position: relative; /* Adicionado */
}

.grafico-container {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  margin-bottom: 300px; /* Adicionado espaço entre o gráfico e o footer */
  padding: 20px; /* Adicionado padding para melhor espaçamento */
}

.grafico {
  width: 500px; 
  height: 300px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Opcional: adiciona uma sombra suave */
  padding: 20px; /* Opcional: adiciona um padding interno */
  background-color: white; /* Opcional: garante um fundo branco */
  border-radius: 8px; /* Opcional: adiciona bordas arredondadas */
}
</style>