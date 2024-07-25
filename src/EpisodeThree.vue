<script setup>
import { computed, ref } from "vue";

const assignments = ref([
  { name: "Finish project", complete: false, id: 1 },
  { name: "Read Chapter 4", complete: false, id: 2 },
  { name: "Turn in homework", complete: false, id: 3 },
]);

const inProgressAssignments = computed(() => {
  return assignments.value.filter((assignment) => !assignment.complete);
});

const computedAssignments = computed(() => {
  return assignments.value.filter((assignment) => assignment.complete);
});
</script>

<template>
  <section v-show="inProgressAssignments.length">
    <h2 class="font-bold mb-2">In Progress</h2>

    <ul>
      <!-- code below, using computed properties doesn't allow the assignment to flow back to inprogress if unchecked from completed -->
      <!-- <li v-for="assignment in inProgressAssignments" :key="assignment.id"> -->
      <li
        v-for="assignment in assignments.filter((a) => !a.complete)"
        :key="assignment.id"
      >
        <label>
          {{ assignment.name }}
          <input type="checkbox" v-model="assignment.complete" />
        </label>
      </li>
    </ul>
  </section>

  <section v-show="computedAssignments.length" class="mt-8">
    <h2 class="font-bold mb-2">Completed</h2>

    <ul>
      <li
        v-for="assignment in assignments.filter((a) => a.complete)"
        :key="assignment.id"
      >
        <label>
          {{ assignment.name }}
          <input type="checkbox" v-model="assignment.complete" />
        </label>
      </li>
    </ul>
  </section>
</template>

<style scoped></style>
