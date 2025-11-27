<template>
  <div>
    <h1>{{ tit }}</h1>
    <p>{{ numero }} <sup>2</sup>={{ calcularCuadrado }}</p>
    <p>{{ numero }} <sup>2</sup>={{ calcularCuadrado }}</p>
    <p>{{ numero }} <sup>2</sup>={{ calcularCuadrado }}</p>
    <p>{{ numero }} <sup>3</sup>={{ calcularCubo }}</p>
    <p>{{ numero }} <sup>3</sup>={{ obtenerCubo() }}</p>

    <div>
      <button @:click="incremetar()">+1</button>
      <button @:click="decrementar()">-1</button>
      <button v-show="mostrar">Prueba</button>
    </div>
  </div>
</template>

<script>
export default {
  //Propiedad reactiva
  data() {
    return {
      numero: this.inicio,
      titulo: "Contador",
      exp: 2,
    };
  },
  methods: {
    obtenerCuadra() {
      console.log("Entro a obtener cuadrado");
      return this.numero * this.numero;
    },
    obtenerCubo() {
      console.log("Entro a obtener cuadrado");
      return this.numero * this.numero * this.numero;
    },
    incremetar() {
      console.log(this.tit);
      this.numero++;
    },
    decrementar() {
      this.numero--;
    },
  },
  computed: {
    calcularCuadrado() {
      console.log("Entro a propiedad computada");
      return this.numero * this.numero;
    },
    calcularCubo() {
      console.log("Entro a propiedad computada");
      return this.numero * this.numero * this.numero;
    },
  },
  /*props: ["tit","inicio","mostrar"], Declaracion basica de props*/
  props: {
    tit: String,
    inicio: {
      type: Number,
      default: 99,
      validator(value){
        return value>10;
      }
    },
    mostrar: Boolean,
  },
  /**String, Number, Boolean, Array, Object, Date, Funcion, BigInt */
};
</script>

<style>
</style>