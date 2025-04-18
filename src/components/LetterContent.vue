<script setup lang="ts">
defineProps<{ color: string; letter: string }>();
</script>
<template>
  <div :class="(color, letter)"></div>
</template>
<style scoped>
.k {
  position: relative;
  width: 0;
  height: 0;
  top: 7px;
  border-left: 20px solid transparent;
  border-right: 20px solid transparent;
  border-bottom: 20px solid v-bind(color);
}

.k:after,
.k:before {
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
  left: -30px;
  transform: rotate(-135deg);
}

.q {
  position: relative;
  width: 30px;
  height: 40px;
  background:
    conic-gradient(from -45deg at bottom, transparent 90deg, v-bind(color) 0)15px;
}

.q:before {
  position: absolute;
  content: "";
  top: 0;
  left: -5px;
  width: 40px;
  height: 40px;
  background:
    conic-gradient(from -45deg at bottom, transparent 90deg, v-bind(color) 0);
}

.q:after {
  position: absolute;
  content: "";
  top: 17px;
  left: 11px;
  width: 8px;
  height: 8px;
  background-color: v-bind(color);
  border-radius: 100%;
  box-shadow: -20px -2px v-bind(color), 20px -2px v-bind(color);
}

.j {
  position: relative;
  width: 10px;
  height: 40px;
  background-color: v-bind(color);
}

.j:before {
  position: absolute;
  content: "";
  top: -10px;
  left: 0px;
  width: 0;
  height: 0;
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-top: 5px solid transparent;
  border-bottom: 5px solid v-bind(color);
}

.j:after {
  position: absolute;
  content: "";
  top: 25px;
  left: -5px;
  width: 20px;
  height: 10px;
  background-color: v-bind(color);

}
</style>
