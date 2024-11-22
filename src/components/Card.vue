<script setup lang="ts">
import Suit from "./Suit.vue";
import Rank from "./Rank.vue";

defineProps<{ suit: string; rank: string; color: string }>();
</script>

<template>
  <div class="card">
    <div class="corner top-left">
      <Rank :rank="rank" :color="color" />
      <Suit :suit="suit" />
    </div>

    <div class="middle">
      <div class="content" v-if="Number.isInteger(parseInt(rank))">
        <div v-for="i in parseInt(rank)"><Suit :suit="suit" /></div>
      </div>
    </div>
    <div class="corner bottom-right">
      <Rank :rank="rank" :color="color" />
      <Suit :suit="suit" />
    </div>
  </div>
</template>

<style scoped>
.card {
  width: 8rem;
  height: 11rem;
  margin: 1rem;
  padding: 0.3rem;
  background: #fff;
  border: 1px solid #999;
  border-radius: 5px;
  overflow: hidden;
  box-shadow: 5px 5px 25px #999;
  cursor: pointer;
}

.card:hover {
  margin: 0.5rem 1rem;
}

.middle {
  background: pink;
  width: 100%;
  height: 100%;
}

.content {
  width: 100%;
  height: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-content: space-between;
}
</style>
