<script setup>
import { ref } from "vue";
import ETable from "./ETable.vue";

const expanses = ref([1, 2, 3, 4]);
function addExpanse() {
  expanses.value.push(10);
}
</script>

<template>
  <h1>Welcome, potrachyun</h1>
  <ETable :expanses="expanses" />
  <button @click="addExpanse">Добавить</button>
</template>
