<template>
  <button ref="appButton" class="app-button" @click="scrollToTop">
    <img src="../assets/top-rocket-1.svg" alt="" class="app-button__img" />
  </button>
</template>

<script setup>
import { onMounted, ref, onBeforeUnmount } from 'vue'

const appButton = ref(null)

// Fonction pour faire défiler jusqu'en haut
const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth',
  })
}

// Fonction pour afficher le bouton quand on défile vers le bas
const userScroll = () => {
  if (window.scrollY > 0) {
    appButton.value.classList.add('showButton')
  } else {
    appButton.value.classList.remove('showButton')
  }
}

// Écouteur pour l'événement de défilement
onMounted(() => {
  window.addEventListener('scroll', userScroll)
})

// Retirer l'écouteur lorsque le composant est démonté
onBeforeUnmount(() => {
  window.removeEventListener('scroll', userScroll)
})
</script>

<style>
/* Styles de base pour l'apparence du bouton */
.app-button {
  position: fixed;
  bottom: 20px;
  right: 20px;
  display: none; /* Caché par défaut */
  background: none;
  border: none;
  /* Autres styles comme la couleur, la taille, etc. */
}
.app-button .app-button__img {
  content: url('../assets/top-rocket-1.svg');
}
.app-button:hover {
  bottom: 25px;
  transition: all 0.2s ease-in;
}
.app-button:hover .app-button__img {
  content: url('../assets/top-rocket-2.svg');
  transition: all 0.2s ease-in;
}

.app-button.showButton {
  display: block; /* Montrer le bouton lorsque la classe est ajoutée */
}


</style>
