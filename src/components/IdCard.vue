<script setup>
import { computed } from 'vue';


const props = defineProps({
    lastName: { type: String, required: true },
    firstName: { type: String, required: true },
    gender: { type: String, required: true }, 
    height: { type: Number, required: true },
  birth: { type: Date, required: true },
    picture: { type: String, required: true }
})


const formattedBirth = computed(() => props.birth.toDateString());


</script>

<template>
      <div class="id-card-container">
        <img :src="picture" alt="Profile picture" class="id-card-img" />
        <div class="id-card-details">
          <p> <strong> First name: </strong>{{ firstName }} </p>
          <p> <strong> Last name: </strong>{{ lastName }} </p>
          <p> <strong> Gender: </strong> {{ gender }}</p>
          <p> <strong> Height: </strong> {{ height }}</p>
          <p> <strong> Birth: </strong> {{ formattedBirth }}</p>
        </div>
      </div>
</template>

<style scoped>
 .id-card-container {
   display: flex;
   align-items: center;
    box-shadow: 0 2px 8px rgba(0,0,0,0.08);
   padding: 1rem;
   margin: 1rem;
  border: solid black 1px;
 }
 .id-card-img {
   width: 150px;
   height: 150px;
   object-fit: cover;
   margin-right: 1.5rem;
 }
 .id-card-details {
   flex: 1;
 }

</style>

 