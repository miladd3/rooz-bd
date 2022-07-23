<script setup>
import rooz from '../assets/rooz.webp';
</script>

<template>
  <div class="image">
    <div class="card">
      <img :src="rooz" alt="rooz" class="rooz"/>
    </div>
  </div>
</template>

<style scoped lang="scss">
.image {
  .card {
    padding: 40px;
    box-sizing: border-box;
  }
  
  .rooz {
    width: 100%;
    padding: 10px 10px 40px 10px;
    box-sizing: border-box;
    background: #fff;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.7);
  }
}
</style>
