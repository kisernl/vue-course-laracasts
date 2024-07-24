<script setup>
import { ref } from "vue";

const active = ref(false);

const toggle = () => {
  active.value = !active.value;
};
</script>

<template>
  <button :class="active ? 'text-red' : 'text-green'" @click="toggle">
    Click Me
  </button>
</template>

<style scoped>
.text-red {
  color: red;
}
.text-green {
  color: green;
}
</style>
