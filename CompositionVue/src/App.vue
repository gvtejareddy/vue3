<script setup>
import { ref } from 'vue';
let count = ref(0);

const addCount = () => {
  console.log(count.value);
  count.value = count.value + 1;
}

const subCount = () => {
  console.log(count.value);
  if (count.value > 0)
    count.value = count.value - 1;
}
</script>

<template>
  <div>Check Vue 3 For Composition</div>
  <div> {{ count }}</div>
  <button @click=addCount>Plus</button>
  <button @click=subCount>Sub</button>
</template>

<style scoped></style>
