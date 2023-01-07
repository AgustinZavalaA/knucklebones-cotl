<template>
  <v-card
    :loading="loading"
    :disabled="loading || disabled"
    @click="randomizeDice(randomDiceValue)"
    style="height: 100%"
    class="dice_card"
  >
    <v-card-text class="d-flex align-center justify-center h-100">
      <h1>{{ randomDiceValue ? randomDiceValue : randomDiceText }}</h1>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "PlayableDice",
  props: {
    disabled: {
      type: Boolean,
      default: false,
    },
    enemyDiceTurn: {
      type: Boolean,
      default: false,
    },
  },
  emits: ["dice-clicked"],
  data() {
    return {
      randomDiceValue: 0,
      randomDiceText: "Click to roll",
      loading: false,
    };
  },
  methods: {
    async randomizeDice() {
      // load for 2 seconds then update the dice value
      this.loading = true;
      this.randomDiceText = "Rolling...";
      this.randomDiceValue = 0;

      await new Promise((resolve) => setTimeout(resolve, 2000));

      this.randomDiceValue = Math.floor(Math.random() * 6) + 1;
      this.loading = false;
      this.$emit("dice-clicked", this.randomDiceValue);
    },
  },
  watch: {
    enemyDiceTurn() {
      if (this.enemyDiceTurn) {
        this.randomizeDice();
      }
    },
  },
};
</script>

<style scoped>
.dice_card:hover {
  background-color: #f1faee;
  color: #1d3557;
}
</style>
