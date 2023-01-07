<template>
  <v-container>
    <h1 style="text-align: center">
      {{ lambTurn ? "Lamb" : "Enemy " }} Turn {{ currentDice }}
    </h1>
    <v-row>
      <v-col cols="2">
        <playable-dice @dice-clicked="diceClicked" :disabled="!lambTurn" />
      </v-col>
      <v-col cols="8">
        <game-board />
        <game-board />
      </v-col>
      <v-col cols="2">
        <playable-dice
          @dice-clicked="diceClicked"
          :disabled="true"
          :enemy-dice-turn="!lambTurn"
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import PlayableDice from "@/components/PlayableDice.vue";
import GameBoard from "@/components/GameBoard.vue";

export default {
  name: "KnucklebonesGame",
  components: { PlayableDice, GameBoard },
  emits: ["move-made"],
  data() {
    return {
      lambTurn: true,
      currentDice: 0,
    };
  },
  mounted() {
    this.lambTurn = Math.random() >= 0.5;
  },
  methods: {
    diceClicked(diceValue) {
      this.currentDice = diceValue;
      // this emits should be clled when the center board is clicked
      this.lambTurn = !this.lambTurn;
      this.$emit("move-made", diceValue, !this.lambTurn);
    },
  },
};
</script>

<style scoped></style>
