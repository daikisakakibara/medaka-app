<script setup lang="ts">
const switchTab = ref(0);

function increment() {
  switchTab.value++;
  console.log(switchTab.value);
}
</script>

<template>
  <div class="flex flex-col items-center justify-center min-h-screen">
    <div class="mx-auto max-w-2xl lg:text-center" v-show="switchTab === 0">
      <p class="mt-2 text-3xl tracking-tight text-gray-600 sm:text-4xl">
        you're Medaka eggs.
      </p>
      <p class="mt-6 text-3xl tracking-tight text-gray-600 sm:text-4xl">
        あなたはメダカの卵です。
      </p>
    </div>
    <div class="mx-auto max-w-2xl lg:text-center" v-show="switchTab === 1">
      <p class="mt-2 text-3xl tracking-tight text-gray-600 sm:text-4xl">
        ベイベー
      </p>
      <p class="mt-6 text-3xl tracking-tight text-gray-600 sm:text-4xl">
        ベイベー
      </p>
    </div>
    <div class="mt-8">
      <div class="flex flex-row gap-4">
        <UButton @click="increment" color="white" variant="solid" size="lg"
          >戻る</UButton
        >
        <UButton
          @click="increment"
          class="blinking-button"
          color="fuchsia"
          variant="solid"
          size="lg"
          >次へ</UButton
        >
      </div>
    </div>
  </div>
</template>

<style>
@keyframes blink {
  0% {
    opacity: 1;
  }
  50% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

.blinking-button {
  animation: blink 4s infinite;
}
</style>
