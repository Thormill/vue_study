<script setup>
import { computed } from "vue";

const props = defineProps({
  expanses: {
    type: Array,
  },
});

const total = computed(() => {
  if (!props.expanses || props.expanses.length === 0) {
    return 0;
  }
  return props.expanses.reduce((accumulator, currentValue) => {
    return accumulator + currentValue;
  }, 0);
});
</script>

<template>
  <h2>Таблица расходов</h2>
  <table>
    <tr v-for="e in props.expanses">
      <td>
        {{ e }}
      </td>
    </tr>
    <tr>
      <td>
        {{ total }}
      </td>
    </tr>
  </table>
</template>
