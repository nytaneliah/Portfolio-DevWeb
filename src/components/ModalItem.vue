<template>
  <!-- Modal overlay that closes when clicked outside the content -->
  <div class="modal__overlay" @click.self="close">
    <div class="modal__content">
      <!-- Close button for the modal -->
      <button @click="close" class="modal__close">X</button>

      <!-- Title of the creation -->
      <h2>{{ creation.title }}</h2>

      <!-- Technologies used in the creation -->
      <p><strong>Technologies :</strong> {{ creation.technologies.join(', ') }}</p>

      <!-- Description of the creation -->
      <p>{{ creation.description }}</p>

      <!-- Link to view the creation -->
      <a :href="creation.link" target="_blank" class="modal__link">Voir la réalisation</a>

      <!-- Images associated with the creation -->
      <div class="modal__images">
        <img
          v-for="(image, index) in creation.images"
          :key="index"
          :src="image"
          class="modal__img"
        />
      </div>

      <!-- Date of creation -->
      <p><strong>Date de création :</strong> {{ creation.date }}</p>

      <!-- Link to view the creation (duplicate) -->
      <a :href="creation.link" target="_blank" class="modal__link">Voir la réalisation</a>
    </div>
  </div>
</template>


<script setup>
// Importing the necessary functions from Vue
const { creation } = defineProps({
  // Defining the prop 'creation' which is an object
  creation: Object,
})

// Defining the emits for the component
const emit = defineEmits(['close'])

// Function to emit the 'close' event
const close = () => {
  emit('close')
}
</script>


<style scoped>
/* Styles for the modal overlay */
.modal__overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

/* Styles for the modal content */
.modal__content {
  background: var(--color-background);
  padding: 20px;
  max-width: 600px;
  width: 90%;
  border-radius: 5px;
  position: relative;
  overflow-y: auto;
  max-height: 80vh;
  display: flex;
  flex-direction: column;
  gap: 3vh;
  box-shadow: 0px 4px 8px 5px var(--color-shadow);
}

/* Styles for the close button */
.modal__close {
  position: absolute;
  top: 10px;
  right: 10px;
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
  color: var(--color-link);
}

/* Styles for the images container */
.modal__images {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
}

/* Styles for each image */
.modal__img {
  max-width: 100%;
  height: auto;
  max-height: 80vh;
}

/* Styles for the link to view the creation */
.modal__link {
  color: var(--color-link-active);
  font-weight: bold;
}
</style>

