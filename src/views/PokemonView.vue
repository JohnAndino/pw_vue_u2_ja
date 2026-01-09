<template>
  <PokemonImagen
    v-if="mostrar && pokemonGanador !== null"
    :pokemonId="pokemonGanador"
  />

  <PokemonOpciones
    :listaPokemons="pokemonArr"
    @seleccionado="evaluarGanador"
  />

  <button @click="destruirImagen">Destruir</button>

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
      mensaje: null,
      mostrar: true,
    };
  },
  mounted() {
    this.iniciarJuego();
  },
  methods: {
    async iniciarJuego() {
      this.pokemonArr = await obtenerVectorPokemonFachada();
      const idAleatorio = obteneAleatorioFachada(0, 3);
      this.pokemonGanador = this.pokemonArr[idAleatorio].id;
    },
    evaluarGanador(id) {
      this.mensaje = id === this.pokemonGanador ? "Ganaste" : "Perdiste";
    },
    destruirImagen() {
      this.mostrar = false;
    },
  },
};
</script>

<style>
button {
  margin-top: 10px;
}
</style>
