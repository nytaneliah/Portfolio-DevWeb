<template>
  <!-- Button that scrolls the page to the top when clicked -->
  <button ref="appButton" class="app-button" @click="scrollToTop">
    <img src="../assets/top-rocket-1.svg" alt="" class="app-button__img" />
  </button>
</template>

<script setup>
import { onMounted, ref, onBeforeUnmount } from 'vue'
import { useRouter } from 'vue-router'

const appButton = ref(null) // Reference to the button element

const router = useRouter()

// Function to smoothly scroll the page to the top
const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth',
  })
  // Redirect to home page after a short delay
  setTimeout(() => {
    router.push('/')
  }, 1000)
}

// Function to show the button when the user scrolls down
const userScroll = () => {
  if (window.scrollY > 0) {
    appButton.value.classList.add('showButton') // Show button when scrolled
  } else {
    appButton.value.classList.remove('showButton') // Hide button at the top
  }
}

// Add scroll event listener when the component is mounted
onMounted(() => {
  window.addEventListener('scroll', userScroll)
})

// Remove scroll event listener when the component is unmounted
onBeforeUnmount(() => {
  window.removeEventListener('scroll', userScroll)
})
</script>

<style>
/* Base styles for the button appearance */
.app-button {
  position: fixed;
  bottom: 20px;
  right: 20px;
  display: none; /* Hidden by default */
  background: none;
  border: none;
  z-index: 1000;

  /* Additional styles like color, size, etc. */
}

.app-button .app-button__img {
  content: url('../assets/top-rocket-1.svg');
}

.app-button:hover {
  bottom: 25px; /* Lift button on hover */
  transition: all 0.2s ease-in;
  cursor: pointer;
}

.app-button:hover .app-button__img {
  content: url('../assets/top-rocket-2.svg'); /* Change image on hover */
  transition: all 0.2s ease-in;
}

.app-button.showButton {
  display: block; /* Show the button when this class is added */
}
</style>
