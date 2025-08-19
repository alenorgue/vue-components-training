<script setup>
import { computed } from 'vue';
import Rating from './Rating.vue'


const props = defineProps({
    name: {type:String, required:true},
    img: {type:String, required:true},
    rating: {type:Number, required: true},
    car: {
        type: Object,
        required: true}

})

</script>

<template>
 
     <div class="driver-card">
        <img :src="img" alt="name" class="id-card-img" />
        <div class="id-card-details">
    
      <h2> {{ name }} </h2>
      <Rating :rate="rating" />
      <p> {{ car.model }} {{ car.licensePlate }}</p>
    </div>
    </div>
 
</template>

<style scoped>

 .driver-card {
   display: flex;
   align-items: center;
    box-shadow: 0 2px 8px rgba(0,0,0,0.08);
   padding: 1rem;
   margin: 1rem;
  border: solid 1px;
  justify-content: center;
  background-color: lightblue;
  color: white;
 }
 .id-card-img {
   width: 150px;
   height: 150px;
   object-fit: cover;
   margin-right: 1.5rem;
    border-radius: 50%;
 }
 

</style>
