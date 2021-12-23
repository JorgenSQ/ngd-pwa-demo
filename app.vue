<template>
  <div  flex="~ row">
    <h1>Counter: {{ count }}</h1>
    <Button label="Press me" icon="pi pi-check" @click="count++"></Button>
    <h1>pos: {{ x }}, {{ y }}</h1>
  </div>
</template>

<script setup lang="ts">
  import { ref } from "vue";
  import { useMouse } from '@vueuse/nuxt/node_modules/@vueuse/core';

  const count = ref(0);
  const { x, y } = useMouse();
</script>
