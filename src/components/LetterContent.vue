<script setup lang="ts">
const props = defineProps<{ color: string; letter: string }>();
</script>
<template>
  <div :class="(color, letter)"></div>
</template>
<style scoped>
.k {
  position: relative;
  width: 0;
  height: 0;
  border-left: 20px solid transparent;
  border-right: 20px solid transparent;
  border-bottom: 20px solid v-bind(color);
}

.k:after {
  position: absolute;
  content: "";
  top: 7px;
  left: 0;
  width: 0;
  height: 0;
  border-left: 15px solid transparent;
  border-right: 15px solid transparent;
  border-bottom: 15px solid v-bind(color);
  transform: rotate(135deg);
}

.k:before {
  position: absolute;
  content: "";
  top: 7px;
  left: -30px;
  width: 0;
  height: 0;
  border-left: 15px solid transparent;
  border-right: 15px solid transparent;
  border-bottom: 15px solid v-bind(color);
  transform: rotate(-135deg);
}
</style>
