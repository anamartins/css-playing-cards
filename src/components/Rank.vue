<script setup lang="ts">
defineProps<{ rank: string; color: string }>();
</script>

<template>
  <div class="rank" :class="color">{{ rank }}</div>
</template>

<style scoped>
.rank {
  font-size: 2rem;
  margin-left: 3px;
}

.inverted {
  transform: rotate(180deg);
}

.red {
  color: red;
}

.black {
  color: black;
}
</style>
