<script setup>
import IdCard from './components/IdCard.vue'
import Random from './components/Random.vue'
</script>

<template>
  <h1>Creación de componentes con Vue</h1>
  <p>Crea a conitnuación todos los componentes del ejercicio.</p>
      <h1>1- ID Cards</h1>
<div>
  <IdCard
    picture="https://randomuser.me/api/portraits/men/44.jpg"
    first-name="John"
    last-name="Doe"
    gender="male"
    :height="178"
  :birth="new Date('1992-07-14')"
  />
 <IdCard
  last-name='Delores '
  first-name='Obrien'
  gender='female'
  :height="172"
  :birth='new Date("1988-05-11")'
  picture="https://randomuser.me/api/portraits/women/44.jpg"
/>
</div>
  <h1>2- Random number</h1>
<div>
  <Random :min="1" :max="6" />
  <Random :min="1" :max="100" />
</div>
</template>

<style scoped>
h2 {margin: 1rem 0;}
</style>
