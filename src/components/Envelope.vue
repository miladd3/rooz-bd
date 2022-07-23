<script setup>
import envelope from '../assets/env.png';
</script>

<template>
  <div class="envelope" v-bind="$attrs">
    <img :src="envelope" alt="envelope" />
    <h1>
      Open the Envelope
    </h1>
  </div>
</template>

<style scoped lang="scss">
.envelope {
  width: 100%;
  padding: 50px;
  box-sizing: border-box;
  img {
    width: 100%;
    box-sizing: border-box;
  }

  h1 {
    font-weight: bold;
    line-height: 2;
    white-space: nowrap;
  }
}
</style>
