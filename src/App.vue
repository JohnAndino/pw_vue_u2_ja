<template>
  <div>
    <!-- <ContadorView/> -->
    <!--DirectivasView/--> 
    <!-- <PreguntaView/> -->
    <PokemonView/>
  </div>
</template>

<script>
import ContadorView from '../src/views/ContadorView.vue';
import DirectivasView from './views/DirectivasView.vue';
import PreguntaView from './views/PreguntaView.vue';
import PokemonView from "./views/PokemonView.vue"
export default {
  components: { 
    ContadorView, 
    DirectivasView,
    PreguntaView,
    PokemonView
  },
};
</script>

<style >
  h1 {
    color: black;
  } 

</style>