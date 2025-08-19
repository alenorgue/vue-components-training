<script setup>
import { ref } from "vue";

// Recibimos el array de imágenes desde App.vue
const props = defineProps({
  images: {
    type: Array,
    required: true,
  },
});

const currentIndex = ref(0);

function next() {
  currentIndex.value = (currentIndex.value + 1) % props.images.length;
}

function prev() {
  currentIndex.value =
    (currentIndex.value - 1 + props.images.length) % props.images.length;
}
</script>

<template>
  <div class="carousel">
     <button @click="prev">Left</button>
     <div>
      <img :src="images[currentIndex]" alt="Imagen carrusel" />
    </div>
     <button @click="next">Right</button>
  </div>
</template>

<style scoped>
.carousel{
    display: flex;
    align-items: flex-end;
    gap: 5px;
}
img{
    width: 350px;
}

</style>
