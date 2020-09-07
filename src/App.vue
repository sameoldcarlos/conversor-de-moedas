<template>
  <div id="app">
    <div class="limitador cabecalho">
      <h1 class="text-center">Conversor de Moedas</h1>
    </div>
    <div id="conversor">
      <div class="linha">    
      <Conversor moeda-a="USD" moeda-b="BRL"/>
      <Conversor moeda-a="BRL" moeda-b="USD"/>
    </div>
    <div class="linha">
      <Conversor moeda-a="CAD" moeda-b="BRL"/>
      <Conversor moeda-a="BRL" moeda-b="CAD"/>
    </div>
    <div class="linha">
      <Conversor moeda-a="EUR" moeda-b="BRL"/>
      <Conversor moeda-a="BRL" moeda-b="EUR"/>
    </div>
    </div>
    <div class="limitador rodape">
      <h3 class="text-center">Desenvolvido com <span class="fas fa-heart"></span> por <a href="https://www.instagram.com/sameoldcarlos">Carlos Alves</a></h3>
    </div>
    
  </div>
</template>

<script>

import Conversor from "./components/Conversor.vue"
export default {
  name: 'App',
  components: {
    Conversor
  }
}
</script>

<style>
#app {    
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background: repeating-linear-gradient(
45deg,
#c9c8c8,
#c9c8c8 3px,
#a3a3a3 3px,
#a3a3a3 6px)
}
a, a:hover{
  color: #ffffff;
  text-decoration: none;
}
.limitador {
  top: 0;
  width: 100%;
  height: 80px;
  background-color: #000000;
  color: #ffffff;
  display: table;
}

#conversor {
  margin: 60px auto;
  max-width: 900px;
}
.linha {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
  gap: 20px;
  margin-bottom: 30px;
  
}

.text-center {
  vertical-align: middle;
  text-align: center;
  display:table-cell;
  
}
</style>
