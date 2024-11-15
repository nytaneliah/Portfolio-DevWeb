<template>
  <section id="contact">
    <h2>Contactez-moi</h2>
    <h3>Pour donner vie à vos idées numériques</h3>
    <form @submit.prevent="handleSubmit" id="contact-form">
      <input type="hidden" name="contact_number" value="697483" />
      <label for="user_name">Nom</label>
      <input type="text" v-model="form.user_name" id="user_name" name="user_name" required />

      <label for="user_email">Email</label>
      <input
        type="email"
        v-model="form.user_email"
        id="user_email"
        name="user_email"
        @input="validateEmail"
        required
      />
      <span v-if="!isEmailValid && form.user_email" class="error-message">
        Veuillez entrer un email valide.
      </span>

      <label for="message">Message</label>
      <textarea v-model="form.message" id="message" name="message" required></textarea>

      <button type="submit">Envoyer</button>
    </form>
    <div v-if="isSuccess" class="success-message">
      Votre message a bien été envoyé à {{ myEmailAddress }}
    </div>
    <div v-if="isError" class="error-message">Une erreur est survenue. Veuillez réessayer.</div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

// Reactive state for the form data and submission status
const form = ref({
  user_name: '',
  user_email: '',
  message: '',
})
const myEmailAddress = ref(import.meta.env.VITE_APP_EMAIL_ADDRESS)
const isSuccess = ref(false)
const isError = ref(false)
const isEmailValid = ref(true) // Tracks email validity

// Validate email format
const validateEmail = () => {
  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
  isEmailValid.value = emailRegex.test(form.value.user_email)
}

// Simulate sending the form (e.g., successful submission after 2 seconds)
const sendForm = () => {
  return new Promise((resolve) => {
    setTimeout(() => {
      // Simulate successful form submission
      resolve()
    }, 2000) // Simulate a 2-second delay for form submission
  })
}

// Handle form submission
const handleSubmit = () => {
  sendForm()
    .then(() => {
      // If the form is sent successfully, show the success message
      isSuccess.value = true
      isError.value = false
      // Reset form data
      form.value = {
        user_name: '',
        user_email: '',
        message: '',
      }
    })
    .catch((error) => {
      // Handle error if sending fails
      isSuccess.value = false
      isError.value = true
      console.error('FAILED...', error)
    })
}
</script>

<style scoped>
#contact {
  /* padding-bottom: 60px; */
  height: 100vh;
}
form {
  display: flex;
  flex-flow: column wrap;
  max-width: 500px;
  margin: 0 auto;
  justify-content: center;
  align-items: center;
  gap: 10px;
}

label {
  margin: 10px 0 5px;
}

input,
textarea {
  width: 100%;
  padding: 10px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
}

button {
  padding: 10px 20px;
  background-color: #28a745;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #218838;
}

.success-message {
  margin-top: 20px;
  color: green;
}

.error-message {
  margin-top: 20px;
  color: red;
}
</style>
