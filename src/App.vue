<template>
  <v-app>
    <v-main class="app">
      <the-header />
      <the-punctuation
        :lamb-punctuation="lambPunctuation"
        :enemy-punctuation="enemyPunctuation"
        :number-moves="numberMoves"
      />
      <knucklebones-game />
      <the-footer />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import KnucklebonesGame from "@/components/KnucklebonesGame.vue";
import TheHeader from "@/components/layouts/TheHeader.vue";
import ThePunctuation from "@/components/layouts/ThePunctuation.vue";
import TheFooter from "@/components/layouts/TheFooter.vue";

export default defineComponent({
  name: "App",

  components: {
    TheHeader,
    KnucklebonesGame,
    ThePunctuation,
    TheFooter,
  },

  data() {
    return {
      lambPunctuation: 0,
      enemyPunctuation: 0,
      numberMoves: 0,
    };
  },
});
</script>

<style>
.app {
  background-color: #1d3557;
  color: #f1faee;
}
</style>
