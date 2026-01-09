<template>
  <PokemonImagen :pokemonId="pokemonGanador" />
  <PokemonOpciones
    @seleccionado="evaluarGanador($event)"
    :listaPokemons="pokemonArr"
  />
  <p v-if="mensaje">{{ mensaje }}</p>
 
</template>
 
<script>
import {
  obteneAleatorioFachada,
  obtenerVectorPokemonFachada,
} from "@/clients/PokemonClient";
import PokemonImagen from "@/components/PokemonImage.vue";
import PokemonOpciones from "@/components/PokemonOpciones.vue";
export default {
  components: {
    PokemonImagen,
    PokemonOpciones,
  },
  data() {
    return {
      pokemonArr: [],
      pokemonGanador: null,
      mensaje:null,
    };
  },
  /*Crea el componente*/
  beforeCreate() {

    console.log("beforeCreate: apenas inicia la instancia del componente");
  },
  create(){
    console.log("create: se ejecuta cuando ya se han ejecutado el data, computed, methods Y WATCH ")
  },

  /* Monta el componente: renderiza o visualiza el componente */

  beforeMount() {
    console.log("beforeMounted: ");
  },
  mounted() {
    console.log("componente¡ montado");
    this.iniciarJuego();
  },
  methods: {
    async iniciarJuego() {
      this.pokemonArr = await obtenerVectorPokemonFachada();
      const idAleatorio = obteneAleatorioFachada(0, 3);
      this.pokemonGanador = this.pokemonArr[idAleatorio].id;
    },
    evaluarGanador(idGanador) {
      console.log("valor recibido desde el padre");
      console.log(idGanador);
      if (idGanador === this.pokemonGanador) {
        this.mensaje="ganaste";
      } else {
        this.mensaje="perdiste";
      }
    },
  },
};
</script>
 
<style>
 
</style>