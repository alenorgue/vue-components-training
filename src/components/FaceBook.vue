<script setup>
import profiles from "../data/berlin.json";
import { computed, ref } from 'vue';

</script>

<template>
 <div v-for="(profile, index) in profiles" :key="index" class="id-card-container">
        <img :src="profile.img" alt="Profile picture" class="id-card-img" />
        <div class="id-card-details">
          <p> <strong> First name: </strong>{{ profile.firstName }} </p>
          <p> <strong> Last name: </strong>{{ profile.lastName }} </p>
          <p> <strong> Country: </strong> {{ profile.country }}</p>
          <p> <strong> Type: </strong>  <span v-if="profile.isStudent">Student</span>
        <span v-else>Teacher</span> </p>
         
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
  border: solid 1px;
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
