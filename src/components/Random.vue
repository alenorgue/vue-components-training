<script setup>
import { computed } from 'vue';


const props = defineProps({
      min: {type:Number, required: true},
    max: {type:Number, required: true}
})

const randomValue = computed(() => {
    // Ensure min and max are integers
    const min = Math.ceil(props.min);
    const max = Math.floor(props.max);
    // Generate random integer between min and max (inclusive)
    return Math.floor(Math.random() * (max - min + 1)) + min;
});

</script>

<template>
      <div class="id-card-container">
       <p> Random value between {{ min }} and {{ max }} => {{ randomValue }}</p>
        </div>
</template>

<style scoped>
 .id-card-container {
   display: flex;
   align-items: center;
    box-shadow: 0 2px 8px rgba(0,0,0,0.08);
   padding: 1rem;
   margin: 1rem;
  border: solid 1px;
 }

</style>

 