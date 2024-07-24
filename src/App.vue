<script setup>
import { ref } from "vue";

const assignments = ref([
  { name: "Finish project", complete: false },
  { name: "Read Chapter 4", complete: false },
  { name: "Turn in homework", complete: false },
]);
</script>

<template>
  <section>
    <h2 class="font-bold mb-2">Assignments</h2>

    <ul>
      <li v-for="assignment in assignments">
        <label>
          {{ assignment.name }}
          <input type="checkbox" v-model="assignment.complete" />
        </label>
      </li>
    </ul>
    <pre>
      {{ assignments }}
    </pre>
  </section>
</template>

<style scoped></style>
