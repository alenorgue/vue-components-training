<script setup>
import { ref, computed } from 'vue';

const props = defineProps({
  color: { type: String, required: true },
  value: { type: Number, required: true }
});

const localValue = ref(props.value);

const bgColor = computed(() => {
  let r = 0, g = 0, b = 0;
  if (props.color === "r") r = localValue.value;
  if (props.color === "g") g = localValue.value;
  if (props.color === "b") b = localValue.value;
  return `rgb(${r},${g},${b})`;
});

</script>

<template>
  <div>
    <div class="color-box" :style="{ backgroundColor: bgColor }"></div>
  <label>{{ color.toUpperCase() }}: </label>
    <input type="number" min="0" max="255" v-model="localValue" @input="$emit('update:value', Number(localValue))" />
  </div>
</template>

<style scoped>
 .color-box {
  border: solid white 2px;
  margin: 1rem;
    padding: 1rem;
    color: white;
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 30px;
    height: 30px;
 }

</style>
