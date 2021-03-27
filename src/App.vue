<template>
  <div id="app">
    <h1 class="title">Conversor de Moedas</h1>
    <div class="row">
      <Converter coin-a="USD" coin-b="BRL" />
      <Converter coin-a="BRL" coin-b="USD" />
    </div>
    <div class="row">
      <Converter coin-a="CAD" coin-b="BRL" />
      <Converter coin-a="BRL" coin-b="CAD" />
    </div>
    <div class="row">
      <Converter coin-a="EUR" coin-b="BRL" />
      <Converter coin-a="BRL" coin-b="EUR" />
    </div>
  </div>
</template>

<script>
import Converter from "./components/Converter";
export default {
  name: "App",
  components: {
    Converter,
  },
};
</script>

<style>
#app {
  max-width: 900px;
  margin: auto;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  margin-bottom: 60px;
}
.title {
  color: #6730ec;
  font-size: 25px;
  text-align: center;
}
.row {
  margin-top: 40px;
  display: flex;
  justify-content: space-around;
}
</style>