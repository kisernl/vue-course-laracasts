<script setup>
import AppButton from "./components/icons/AppButton.vue";
</script>

<template>
  <app-button :processing="true">Submit</app-button>
</template>

<style>
@keyframes spinner {
  to {
    transform: rotate(360deg);
  }
}
.is-loading {
  color: transparent;
}

.is-loading:before {
  content: "";
  box-sizing: border-box;
  position: absolute;
  top: 50%;
  left: 50%;
  width: 20px;
  height: 20px;
  margin-top: -10px;
  margin-left: -10px;
  border-radius: 50%;
  border: 2px solid #ccc;
  border-top-color: #000;
  animation: spinner 0.6s linear infinite;
}
</style>
