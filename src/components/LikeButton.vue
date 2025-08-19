<script setup>
import { ref } from 'vue'

const likes = ref(0)
const colors = ['purple','blue','green','yellow','orange','red']
const colorIndex = ref(0)

function handleClick() {
	likes.value++
	colorIndex.value = (colorIndex.value + 1) % colors.length
}
</script>

<template>
	<button
		:style="{ backgroundColor: colors[colorIndex] }"
		@click="handleClick"
		class="like-btn"
	>
		{{ likes }} Likes
	</button>
</template>

<style scoped>
.like-btn {
	color: white;
	border: none;
	padding: 0.5rem 1.5rem;
	font-size: 1.2rem;
	border-radius: 8px;

}
</style>

 