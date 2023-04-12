<template>
  <h1 v-if="!pokemon">Please wait...</h1>

  <div v-else>
      <h1>Who is this Pokemon?</h1>
      
      <PokemonPicture />
      <PokemonOptions />

      <template v-if="showAnswer">
          <h2 class="fade-in">{{ message }}</h2>
          <button @click="newGame">
              New Game
          </button>
      </template>

  </div>
  
</template>


<script setup lang="ts">
import { usePokemons } from '../composables/usePokemons';

import PokemonOptions from '../components/PokemonOptions.vue';
import PokemonPicture from '../components/PokemonPicture.vue';


const { pokemon, showAnswer, message, mixPokemonArray, newGame } = usePokemons();
  
mixPokemonArray();

</script>

