<script setup>
import { computed } from 'vue';


const props = defineProps({
     r: {type:Number, required: true},
    g: {type:Number, required: true},
    b: {type:Number, required: true}
})

const bgColor = computed(() => {
    return `rgb(${props.r}, ${props.g}, ${props.b})`;
});

</script>

<template>
      <div class="colorbox-container" :style="{ backgroundColor: bgColor }">
       <p> rgb {{ r }} {{ g }} {{ b }} </p>
         <p> hex {{ '#' + ((1 << 24) + (props.r << 16) + (props.g << 8) + props.b).toString(16).slice(1) }} </p>
        </div>
</template>

<style scoped>
 .colorbox-container {
  border: solid white 2px;
  margin: 1rem;
    padding: 1rem;
    color: white;
    display: flex;
    flex-direction: column;
    align-items: center;
 }

</style>
