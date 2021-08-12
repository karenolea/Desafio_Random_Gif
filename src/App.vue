<template>
  <div >
    <h1>Random Gif Cat</h1>

    <div class="formulario">
      <label for="">Titulo: </label>
      <input v-model="titulo" />

      <div>
        <label for="">Filtro: </label>
        <select class="filtro" v-model="fitro">
          <option value="sepia">sepia</option>
          <option value="mono">mono</option>
          <option value="negative">negative</option>
          <option value="paint">paint</option>
          <option value="pixel">pixel</option>
        </select>
      </div>

      
      <div class="colorCirculo">
        <label for="">Color:</label> 
        <select class="color" v-model="color">
          <option value="red">rojo</option>
          <option value="blue">azul</option>
          <option value="green">verde</option>
          <option value="white">blanco</option>
          <option value="yellow">amarillo</option>
        </select> 
        <div class="circulo" :style="{ background: color }"></div>
      </div>

      <label for="">fuente: </label>
      <input v-model="fuente" />
    </div>

    <button @click="gatito">Obtener mi gatito</button>
    <br>
    <img :src="imagen" />
  </div>
</template>

<script>
// import Consulta from "./components/Consulta.vue";

export default {
  name: "App",
  components: {
    // Consulta,
  },
  data() {
    return {
      titulo: "",
      filtro: "",
      color: "",
      fuente: "",
      imagen: "",
    };
  },
  created() {
    this.btn();
  },
  methods: {
    btn() {
      return `https://cataas.com/cat/gif/says/${this.titulo}?filter=${this.filtro}&color=${this.color}&size=${this.fuente}`;
    },
    gatito() {
      this.imagen = this.btn();
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #4a545d;
  background:powderblue;
  padding-bottom: 18rem;
  padding-top: 8rem;
  margin: 0;
  
  
}
label{
  width: 100px;
  margin-top: 1rem;
  display: inline-block;
}
input{
  width: 100px;
   margin-top: 1rem;
   display: inline-block;
}

.formulario{
  background: lightcoral;
  padding: 5rem;
  
}
.circulo {
  width: 28px;
  height: 28px;
  border-radius: 50%;
  border-color: black;
  display: inline-block;
  margin-left: 0.2rem;
  vertical-align: middle;
 
}

button{
  padding: 0.5rem;
  margin: 1rem;
}
.filtro{
  margin-right: 1.8rem;
  height: 1.5rem;
  
}
.color{
  margin-left: 0.4rem;
  height: 2rem;
   
}

</style>
