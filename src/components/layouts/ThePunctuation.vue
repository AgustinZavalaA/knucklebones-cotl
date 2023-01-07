<template>
  <v-container>
    <v-row>
      <v-col>
        <v-card>
          <v-card-title>
            {{ lambPunctuation }}
          </v-card-title>
          <v-card-text> The Lamb </v-card-text>
        </v-card>
      </v-col>
      <v-col>
        <v-card class="moves_card">
          <v-card-title>
            {{ numberMoves }}
          </v-card-title>
          <v-card-text> Moves </v-card-text>
        </v-card>
      </v-col>
      <v-col>
        <v-card>
          <v-card-title>
            {{ enemyPunctuation }}
          </v-card-title>
          <v-card-text> The Enemy </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "ThePunctuation",
  props: ["lambPunctuation", "enemyPunctuation", "numberMoves"],
};
</script>

<style scoped lang="scss">
.moves_card {
  background-color: #457b9d;
  color: #f1faee;
}
</style>
