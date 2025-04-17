<script setup lang="ts">
import Suit from "./Suit.vue";
import Rank from "./Rank.vue";
import LetterContent from "./LetterContent.vue";

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
        <Suit v-for="i in parseInt(rank)" :suit="suit" :class="rank" />
      </div>
      <div class="content" v-else-if="rank === 'A'">
        <Suit :suit="suit" :class="rank" />
      </div>
      <div class="content" v-else>
        <LetterContent :color="color" :letter="rank.toLowerCase()" />
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
  display: flex;
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
  height: calc(100% - 2rem);
  margin: 1rem 0;
  display: flex;
}

.content {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  align-content: space-around;
}
.corner {
  margin-left: 0;
  margin-right: 10px;
}
.bottom-right {
  transform: rotate(180deg);
  margin-right: 0;
  margin-left: 10px;
}
</style>
