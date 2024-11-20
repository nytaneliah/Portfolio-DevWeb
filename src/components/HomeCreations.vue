<template>
  <section id="creations">
    <h2>Mes Créations</h2>
    <div class="creations__gallery">
      <figure
        v-for="(creation, index) in creations"
        :key="index"
        class="creations__item"
        @click="openModal(creation)"
      >
        <img :src="creation.thumbnail" :alt="creation.title" class="creation__img" />
        <h3 class="creation__title">
          {{ creation.title }}
        </h3>
      </figure>
    </div>
    <ModalItem v-if="selectedCreation" :creation="selectedCreation" @close="closeModal" />
  </section>
</template>

<script setup>
import { ref } from 'vue'
import ModalItem from './ModalItem.vue'

const creations = ref([
  // {
  //   title: 'Projet',
  //   thumbnail: '../assets/img/creations/1/projet-1.png',
  //   date: '2023-12-15',
  //   technologies: ['Vue.js', 'CSS', 'JavaScript'],
  //   images: ['../assets/img/creations/projet-1.png', '../assets/img/creations/projet-2.png'],
  //   description: 'Une description plus détaillée de la création...',
  //   link: 'https://example.com/projet',
  // },

  {
    title: 'Curriculum Vitae',
    thumbnail: '/src/assets/img/creations/1/cv-preview-1.png',
    date: '2024-09-09',
    technologies: ['HTML', 'CSS'],
    images: [
      '/src/assets/img/creations/1/cv-preview-1.png',
      '/src/assets/img/creations/1/cv-preview-2.png',
    ],
    description: 'Mon CV est une page HTML / CSS avec un dynamisme basique.',
    link: 'https://github.com/nytaneliah/cv-resume',
  },
  {
    title: 'Cahier des charges',
    thumbnail: '/src/assets/img/creations/2/cahier-des-charges-1.png',
    date: '2024-09-25',
    technologies: [],
    images: [
      '/src/assets/img/creations/2/cahier-des-charges-1.png',
      '/src/assets/img/creations/2/cahier-des-charges-2.png',
      '/src/assets/img/creations/2/cahier-des-charges-3.png',
      '/src/assets/img/creations/2/cahier-des-charges-4.png',
    ],
    description:
      'Ceci est un cahier des charges entièrement rédigé par mes soins pour un ecommerce.',
    link: 'https://drive.google.com/file/d/16cJVnOhwtHy0q8b5PgGADjeSEZJI1vZH/view?usp=drive_link',
  },
  {
    title: 'Dynamisation espace commentaires',
    thumbnail: '/src/assets/img/creations/3/dyn-espace-commentaires-1.png',
    date: '2024-10-21',
    technologies: ['HTML', 'CSS', 'JavaScript'],
    images: [
      '/src/assets/img/creations/3/dyn-espace-commentaires-1.png',
      '/src/assets/img/creations/3/dyn-espace-commentaires-2.png',
    ],
    description:
      'Cette réalisation consiste en une intégration de scripts évenementiels dans une page Web',
    link: 'https://github.com/nytaneliah/DynamiserUnEspaceDeCommentaire',
  },
  {
    title: 'Portfolio',
    thumbnail: '/src/assets/img/creations/4/portfolio-1.png',
    date: '2023-11-17',
    technologies: ['Vue JS 3', 'HTML', 'CSS', 'JavaScript'],
    images: [
      '/src/assets/img/creations/4/portfolio-1.png',
      '/src/assets/img/creations/4/portfolio-2.png',
    ],
    description:
      "Ce portfolio construit à l'aide du framework Vue JS 3 en Composition API est une Sigle Page Application",
    link: 'https://github.com/nytaneliah/Portfolio-DevWeb',
  },
])

const selectedCreation = ref(null)

// Opens the modal and sets the selected creation
const openModal = (creation) => {
  selectedCreation.value = creation
}
// Closes the modal by resetting the selected creation
const closeModal = () => {
  selectedCreation.value = null
}
</script>

<style scoped>
#creations {
  background-image: url('../assets/img/hero-bg-2.svg');
  background-position: bottom;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
  height: auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 60px 15px 15px 15px;
  margin-top: -60px;
  gap: 5vh 10vw;
}

.creations__gallery {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 5vh 10vw;
  max-width: 800px;
  background-color: var(--color-background);
}
/* Media query for screens below 768px */
@media (max-width: 768px) {
  .creations__gallery {
    grid-template-columns: 1fr;
  }
}
.creations__item {
  cursor: pointer;
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.creation__img {
  object-fit: contain;
  height: 300px;
  max-height: 50vh;
  width: 300px;
  max-width: 50vw;
}
.creation__img.creation__img:hover {
  box-shadow: 2px 2px 2px 0 var(--color-border);
}
.creation__title {
  max-width: 300px;
}
</style>
