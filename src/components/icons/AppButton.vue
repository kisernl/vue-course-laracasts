<script setup>
// import { onMounted } from "vue";

// onMounted(alert("Hello"));

import { ref } from "vue";

const processing = ref(true);
</script>

<template>
  <button
    class="bg-gray-200 hover:bg-gray-400 border rounded px-5 py-2 disabled:cursor-not-allowed"
    :disabled="processing"
  >
    <slot />
  </button>
</template>
