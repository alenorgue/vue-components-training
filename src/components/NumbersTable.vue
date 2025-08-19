<script setup>
import { computed, ref } from 'vue';

const props = defineProps({
    limit: { type: Number, required: true },
    
})
const numbers = computed(() => Array.from({ length: props.limit }, (_, i) => i + 1));

</script>

<template>
  <div>
    <p>Limit: {{ limit }}</p>

    <table >
      <tbody>
        <tr>
          <td
            v-for="n in numbers"
            :key="n"
            :style="{ backgroundColor: n % 2 === 0 ? 'red' : 'transparent' }"
          >
            {{ n }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
table {
  border-collapse: collapse;
}
tbody {
  display: grid;
  grid-template-columns: repeat(8, 1fr);
  gap: 0;
}
tr {
  display: contents;
}
td {
  padding: 10px;
  text-align: center;
  width: 50px;
  height: 50px;
  border: 1px solid black;
}
</style>
