<script setup>
import profiles from "../data/berlin.json";
import { computed, ref } from 'vue';

const selectedCountry = ref(null)
const searchText = ref('');

// Computed para extraer países únicos
const uniqueCountries = computed(() => {
  return [...new Set(profiles.map(p => p.country))]
})

// Computed para filtrar usuarios
const filteredProfiles = computed(() => {
  let filtered = profiles;
  if (selectedCountry.value) {
    filtered = filtered.filter(p => p.country === selectedCountry.value);
  }
  if (searchText.value.trim()) {
    const text = searchText.value.toLowerCase();
    filtered = filtered.filter(profile =>
      Object.values(profile).some(val =>
        String(val).toLowerCase().includes(text)
      )
    );
  }
  return filtered;
});
</script>

<template>
<div>
  <button
    @click="selectedCountry = null"
    :class="{ selected: !selectedCountry }"
    class="filter-btn">
    Mostrar todos
  </button>
  <button
    v-for="country in uniqueCountries"
    :key="country"
    @click="selectedCountry = country"
    :class="{ selected: selectedCountry === country }"
    class="filter-btn"
  >
    {{ country }}
  </button>
</div>

<input v-model="searchText" placeholder="Search" />

 <div v-for="(profile, index) in filteredProfiles" :key="index" class="id-card-container">
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

 .filter-btn {
   margin: 0.25rem;
   padding: 0.5rem 1rem;
   border: 1px solid #bbb;
   background: #f5f5f5;
   cursor: pointer;
   border-radius: 4px;
   font-size: 1rem;
   transition: background 0.2s, border 0.2s;
 }
 .filter-btn.selected {
   background: #bde0fe;
   border-color: #2196f3;
   font-weight: bold;
 }
</style>
