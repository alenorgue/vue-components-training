<script setup>
import { ref } from 'vue'

const props = defineProps({
    img: { type: String, required: true },
    imgClicked: { type: String, required: true }
})

const isClicked = ref(false);

function handleClick() {
    isClicked.value = !isClicked.value;
}
</script>

<template>
    <img :src="isClicked ? props.imgClicked : props.img" alt="imagen" @click="handleClick" />
</template>

<style scoped>
img{
    width: 250px;
    height: 250px;
}
</style>

 