<template>
  <div class="pokemon-container">
    <img :src="srcImagen" alt="No se puede ver la imagen" />
  </div>
</template>
 
<script>
import { computed } from "vue";
export default {
  props: {
    pokemonId: {
      type: Number,
      required: true,
    },
  },
  computed: {
    srcImagen() {
      return `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/${this.pokemonId}.svg`;
    },
  },
   /* Desmontaje de un componente */
  beforeUnmount() {
    console.log("beforUnmount: justo antes de que el componente se destrutya");
  },
  unmounted(){
    console.log("unmounted: ya fue removido del DOM y destruido ");

  }, 
};
</script>
 
<style>
img {
  height: 200px;
  right: 100px;
}
.pokemon-container {
  display: flex;
  justify-content: center;
  height: 200px;
}
</style>