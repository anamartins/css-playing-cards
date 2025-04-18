<script setup lang="ts">
defineProps<{ suit: string }>();
</script>

<template>
  <div class="suit" :class="suit"></div>
</template>

<style scoped>
.diamonds {
  background: red;
  position: relative;
  margin: 7px 5px;
  width: 12px;
  height: 12px;
  transform: rotate(45deg);
}

.hearts {
  position: relative;
  padding: 5px;
  width: 15px;
  height: 5px;
}

.hearts:before,
.hearts:after {
  position: absolute;
  content: "";
  left: 12px;
  top: 0;
  width: 8px;
  height: 13px;
  background: red;
  border-radius: 50px 50px 0 0;
  transform: rotate(-45deg);
  transform-origin: 0 100%;
}

.hearts:after {
  left: 5px;
  transform: rotate(45deg);
  transform-origin: 100% 100%;
  background: red;
}

.clubs {
  background: black;
  position: relative;
  margin: 0px 9px 10px;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  box-shadow: -4px 5px black, 4px 5px black;
}

.clubs:after {
  position: absolute;
  content: "";
  top: -2px;
  left: 1px;
  width: 0;
  height: 0;
  border-bottom: 10px solid black;
  border-top: 10px solid transparent;
  border-left: 3px solid transparent;
  border-right: 3px solid transparent;
}

.spades {
  position: relative;
  margin: 10px 11px 10px 7px;
  width: 5px;
  height: 9px;
  transform: rotate(180deg);
  box-shadow: -2px -7px 0px -1px black;
}

.spades:before,
.spades:after {
  position: absolute;
  content: "";
  left: 0;
  top: 0;
  width: 9px;
  height: 13px;
  background: black;
  border-radius: 50px 50px 0 0;
  transform: rotate(-45deg);
  transform-origin: 0 100%;
}

.spades:after {
  left: -8px;
  transform: rotate(45deg);
  background: black;
  transform-origin: 100% 100%;
}
</style>
