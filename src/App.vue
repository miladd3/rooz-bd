<script setup>
import JSConfetti from 'js-confetti';
import Envelope from './components/Envelope.vue';
import Image from './components/Image.vue';
import Text from './components/Text.vue';
import { ref } from 'vue';

const jsConfetti = new JSConfetti();

const addConfetti =  () => {
  return new Promise((resolve) => {
    jsConfetti.addConfetti().then(() => {
      jsConfetti
          .addConfetti({
            emojis: ['🌈', '⚡️', '💥', '✨', '💫', '🌸'],
          })
          .then(() => {
            jsConfetti.addConfetti({
              confettiColors: [
                '#ff0a54',
                '#ff477e',
                '#ff7096',
                '#ff85a1',
                '#fbb1bd',
                '#f9bec7',
              ],
            })
            resolve();
          });
    });
  });
};
const isOpen = ref(false);
const textIsOpen = ref(false);

const onEnvelopeClick = () => {
  isOpen.value = true;

  addConfetti().then(() => {
      textIsOpen.value = true;
  });
};
</script>

<template>
  <div class="app">
    <Envelope @click="onEnvelopeClick" v-if="!isOpen" />
    <template v-if="isOpen">
      <Image />

      <transition >
        <div class="text-overlay" v-if="textIsOpen">
          <Text />
        </div>
      </transition>
    </template>
  </div>
</template>

<style scoped lang="scss">
.app {
  width: 100%;
  height: 100vh;
  position: relative;

  .text-overlay {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    background: rgba(#000, 0.8);
  }
}

/* we will explain what these classes do next! */
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
