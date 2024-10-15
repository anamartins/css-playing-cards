<script setup lang="ts">
import Suit from "./Suit.vue";
import Rank from "./Rank.vue";

defineProps<{ suit: string; rank: string; color: string }>();
</script>

<template>
  <div class="card">
    <Rank :rank="rank" :color="color" />
    <Suit :suit="suit" />
  </div>
</template>

<style scoped>
.card {
  width: 7rem;
  height: 10rem;
  margin: 2rem;
  padding: 1rem;
  background: #fff;
  border: 1px solid #999;
  border-radius: 5px;
  overflow: hidden;
  box-shadow: 5px 5px 25px #999;
}
</style>
