<script setup>
import envelope from '../assets/env.png';
</script>

<template>
  <div class="envelope">
    <img :src="envelope" alt="envelope" />
  </div>
</template>

<style scoped lang="scss">
.envelope {
  img {
    width: 100%;
    box-sizing: border-box;
  }
}
</style>
