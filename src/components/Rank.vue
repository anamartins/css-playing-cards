<script setup lang="ts">
defineProps<{ rank: string; color: string; isInverted: boolean }>();
</script>

<template>
  <div class="rank" :class="color">
    {{ rank }}
  </div>
</template>

<style scoped>
.rank {
  font-size: 2rem;
}

.red {
  color: red;
}

.black {
  color: black;
}
</style>
