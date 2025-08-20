<script setup>
import { computed, ref } from 'vue';

const email = ref("")
const password = ref("")
const nationality = ref("")
const showMessage = ref(false)

const emailValid = ref(null)
const passwordValid = ref(null)

function validateEmail() {
    emailValid.value = /^[^@]+@[^@]+\.[^@]+$/.test(email.value);
}
function validatePassword() {
    passwordValid.value = password.value.length >= 6;
}

function handleClick() {
    showMessage.value = true;
}

const greeting = computed(() => {
    if (nationality.value === 'fr') return 'Bonjour!';
    if (nationality.value === 'de') return 'Hallo!';
    if (nationality.value === 'en') return 'Hello!';
    return '';
});
</script>

<template>
<p>Email</p>
<input v-model="email" type="email" placeholder="Enter your email" @input="validateEmail" />
<p :style="{ color: emailValid === null ? '' : emailValid ? 'green' : 'red' }">
    {{ emailValid === null ? '' : emailValid ? 'Email válido' : 'Email inválido' }}
</p>
<p>Password</p>
<input v-model="password" type="password" placeholder="Enter your password" @input="validatePassword" />
<p :style="{ color: passwordValid === null ? '' : passwordValid ? 'green' : 'red' }">
    {{ passwordValid === null ? '' : passwordValid ? 'Contraseña válida' : 'Contraseña muy corta' }}
</p>
<p>Nationality </p>
<select v-model="nationality">
        <option value="">Select nationality</option>
        <option value="en">English</option>
        <option value="fr">French</option>
        <option value="de">German</option>
</select>
<button @click="handleClick">Mostrar mensaje</button>
<div v-if="showMessage">
    <p>{{ greeting }}</p>
    <p>Your email address is: {{ email }}</p>
    <p>Your password is: Correct </p>
</div>
</template>

<style scoped>

</style>
<!-- PicoCSS CDN link for styling -->
<link rel="stylesheet" href="https://unpkg.com/@picocss/pico@latest/css/pico.min.css"></link>