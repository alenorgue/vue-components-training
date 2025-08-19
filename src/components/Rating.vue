<script setup>
import { computed } from 'vue';


const props = defineProps({
    rate: Number
})

const fillStars = computed(() => Math.round(props.rate));
const emptyStars = computed(() => 5 - fillStars.value);

</script>

<template>
    <div>
    <span class="filled" v-for="r in fillStars">★</span>
    <span class="empty"  v-for="r in emptyStars">☆</span>
    </div>
</template>

<style scoped>
span {
    font-size: 1.2rem;
}

.filled {
    color: gold;
}

.empty {
    color: #ccc;
}
</style>