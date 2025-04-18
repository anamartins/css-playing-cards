<script setup lang="ts">
import Suit from "./Suit.vue";
import Rank from "./Rank.vue";
import LetterContent from "./LetterContent.vue";

defineProps<{ suit: string; rank: string; color: string }>();
</script>

<template>
  <div class="card">
    <div class="card-spin">
      <div class="card-front">
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
      <div class="card-back">
        <div class="checkers"></div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  width: 8rem;
  height: 11rem;
  margin: 1rem;
  padding: 0.1rem;
  cursor: pointer;
  perspective: 1000px;
  background-color: transparent;
}

.card-spin {
  position: relative;
  width: 100%;
  height: 100%;
  transition: transform 0.8s;
  transform-style: preserve-3d;
  border: 1px solid #999;
  border-radius: 5px;
  box-shadow: 5px 5px 25px #999;
}

.card:hover .card-spin {
  transform: rotateY(180deg);
}

.card-front,
.card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
  transform-style: preserve-3d;
}

.card-front {
  display: flex;
  background: #fff;
}

.card-back {
  background-color: deeppink;
  transform: rotateY(180deg);
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

.checkers {
  width: 1rem;
  height: 1rem;
  background-color: #fff;
  box-shadow: 2rem 0 #fff, 4rem 0 #fff, 6rem 0 #fff,
    1rem 1rem #fff, 3rem 1rem #fff, 5rem 1rem #fff, 7rem 1rem #fff,
    0rem 2rem #fff, 2rem 2rem #fff, 4rem 2rem #fff, 6rem 2rem #fff,
    1rem 3rem #fff, 3rem 3rem #fff, 5rem 3rem #fff, 7rem 3rem #fff,
    0rem 4rem #fff, 2rem 4rem #fff, 4rem 4rem #fff, 6rem 4rem #fff,
    1rem 5rem #fff, 3rem 5rem #fff, 5rem 5rem #fff, 7rem 5rem #fff,
    0rem 6rem #fff, 2rem 6rem #fff, 4rem 6rem #fff, 6rem 6rem #fff,
    1rem 7rem #fff, 3rem 7rem #fff, 5rem 7rem #fff, 7rem 7rem #fff,
    0rem 8rem #fff, 2rem 8rem #fff, 4rem 8rem #fff, 6rem 8rem #fff,
    1rem 9rem #fff, 3rem 9rem #fff, 5rem 9rem #fff, 7rem 9rem #fff,
    0rem 10rem #fff, 2rem 10rem #fff, 4rem 10rem #fff, 6rem 10rem #fff;
}
</style>
