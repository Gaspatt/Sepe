<!-- eslint-disable vue/multi-word-component-names -->
<script setup>

import grafico from '@/assets/imagens/grafico.png';

</script>

<template>
  <header>
    <nav>

    </nav>

    <main>
      <div class="main-container">
        <div class="lado01">
          <img class="img" :src="grafico" alt="Gráfico">
        </div>
        <div class="lado02">
        <img class="img" :src="grafico" alt="Gráfico">
      </div>
      </div>
    </main>
  </header>

</template>

<style scoped>
.main-container {
  display: flex;
  flex-direction: row ;
  flex-wrap: wrap;
  height: auto;
  width: 100%;
}

.lado01 {
  width: 40%;
  height: 100%;
  display: flex;
 margin-left: 15%; 
}

.lado02 {
  width: 40%;
  height: 100%;
  display: flex;
  margin-right: 15%;
  margin-left: 5%;
}

</style>