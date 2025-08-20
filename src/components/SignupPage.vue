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
<div class="signup-page">

<p>Email</p>
<input v-model="email" type="email" placeholder="Enter your email" @input="validateEmail" />
<p :style="{ color: emailValid === null ? '' : emailValid ? 'green' : 'red' }">
    {{ emailValid === null ? '' : emailValid ? 'Valid Email' : 'Must be a valid Email' }}
</p>
<p>Password</p>
<input v-model="password" type="password" placeholder="Enter your password" @input="validatePassword" />
<p :style="{ color: passwordValid === null ? '' : passwordValid ? 'green' : 'red' }">
    {{ passwordValid === null ? '' : passwordValid ? 'Password is correct' : 'Password is too short' }}
</p>
<p>Nationality </p>
<select v-model="nationality">
        <option value="">Select nationality</option>
        <option value="en">English</option>
        <option value="fr">French</option>
        <option value="de">German</option>
</select>
<button @click="handleClick">Log in</button>
<div v-if="showMessage && emailValid && passwordValid">
    <p>{{ greeting }}</p>
    <p>Your email address is: {{ email }}</p>
    <p>Your password is: Correct </p>
</div>
</div>
</template>

<style scoped>
.signup-page{
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 8px;
    display: flex;
    flex-direction: column;
}
</style>
