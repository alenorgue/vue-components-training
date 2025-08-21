<script setup>
import { ref, computed } from 'vue';
import SingleColorPicker from './SingleColorPicker.vue'

const r = ref(0);
const g = ref(0);
const b = ref(0);

const rgbColor = computed(() => `rgb(${r.value},${g.value},${b.value})`);
</script>

<template>
  <div>
    <SingleColorPicker color="r" :value="r" @update:value="r = $event" />
    <SingleColorPicker color="g" :value="g" @update:value="g = $event" />
    <SingleColorPicker color="b" :value="b" @update:value="b = $event" />
    <div class="color-box" :style="{ backgroundColor: rgbColor }"></div>
    <p>{{ rgbColor }}</p>
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
