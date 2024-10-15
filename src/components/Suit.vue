<script setup lang="ts">
defineProps<{ suit: string; color: string }>();
</script>

<template>
  <div class="suit" :class="suit"></div>
</template>

<style scoped>
.diamonds {
  background: red;
  position: relative;
  margin: 2px 5px;
  width: 18px;
  height: 18px;
  transform: rotate(45deg);
}

.hearts {
  position: relative;
  width: 18px;
  height: 18px;
}

.hearts:before,
.hearts:after {
  position: absolute;
  content: "";
  left: 13px;
  top: 0;
  width: 13px;
  height: 21px;
  background: red;
  border-radius: 50px 50px 0 0;
  transform: rotate(-45deg);
  transform-origin: 0 100%;
}

.hearts:after {
  left: 0;
  transform: rotate(45deg);
  transform-origin: 100% 100%;
  background: red;
}

.clubs {
  background: black;
  position: relative;
  margin: 2px 5px 10px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  box-shadow:
    -5px 8px black,
    5px 8px black;
}

.clubs:after {
  position: absolute;
  content: "";
  top: 5px;
  left: 3px;
  width: 0;
  height: 0;
  border-bottom: 10px solid black;
  border-top: 10px solid transparent;
  border-left: 3px solid transparent;
  border-right: 3px solid transparent;
}

.spades {
  position: relative;
  margin: 10px 10px 5px;
  width: 8px;
  height: 10px;
  transform: rotate(180deg);
  box-shadow: 3px -7px 0 -1px black;
}

.spades:before,
.spades:after {
  position: absolute;
  content: "";
  left: 7px;
  top: 0;
  width: 12px;
  height: 20px;
  background: black;
  border-radius: 50px 50px 0 0;
  transform: rotate(-45deg);
  transform-origin: 0 100%;
}

.spades:after {
  left: -5px;
  transform: rotate(45deg);
  background: black;
  transform-origin: 100% 100%;
}
</style>
