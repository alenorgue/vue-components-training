<script setup>
import { computed, ref } from 'vue';


const diceImages = [
    '/src/assets/images/dice1.png',
    '/src/assets/images/dice2.png',
    '/src/assets/images/dice3.png',
    '/src/assets/images/dice4.png',
    '/src/assets/images/dice5.png',
    '/src/assets/images/dice6.png'
];

const diceSrc = ref('/src/assets/images/dice-empty.png');
const rolling = ref(false);

function handleClick() {
    diceSrc.value = '/src/assets/images/dice-empty.png';
    rolling.value = true;
    setTimeout(() => {
        const randomIndex = Math.floor(Math.random() * 6);
        diceSrc.value = diceImages[randomIndex];
        rolling.value = false;
    }, 1000);
}

</script>

<template>
        <img :src="diceSrc" alt="Dado" @click="handleClick" />
</template>

<style scoped>
img{
    width: 200px;
}

</style>
