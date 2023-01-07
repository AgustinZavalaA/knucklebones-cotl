<template>
  <v-container>
    <v-row no-gutters v-for="(diceRow, i) in dices" :key="i">
      <v-col v-for="(d, j) in diceRow" :key="j">
        <v-card v-if="d">
          <v-card-text class="d-flex align-center justify-center h-100">
            <h1>{{ d }}</h1>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "GameBoard",
  data() {
    return {
      dices: [
        [1, 2, 3],
        [4, 0, 5],
        [2, 0, 0],
      ],
    };
  },
  methods: {
    transpose(matrix) {
      return matrix[0].map((col, i) => matrix.map((row) => row[i]));
    },
  },
};
</script>

<style scoped></style>
