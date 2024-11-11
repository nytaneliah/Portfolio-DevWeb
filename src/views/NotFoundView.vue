<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <main>
    <div class="container">
      <section>
        <svg xmlns="http://www.w3.org/2000/svg" width="6em" height="6em" viewBox="0 0 36 36">
          <circle
            cx="18"
            cy="26.06"
            r="1.33"
            fill="#ccaa00"
            class="clr-i-outline clr-i-outline-path-1"
          ></circle>
          <path
            fill="#ccaa00"
            d="M18 22.61a1 1 0 0 1-1-1v-12a1 1 0 1 1 2 0v12a1 1 0 0 1-1 1"
            class="clr-i-outline clr-i-outline-path-2"
          ></path>
          <path
            fill="#ccaa00"
            d="M15.062 1.681a3.221 3.221 0 0 1 5.647.002l13.89 25.56A3.22 3.22 0 0 1 31.77 32H4.022a3.22 3.22 0 0 1-2.9-4.759zM2.88 28.198A1.22 1.22 0 0 0 4 30h27.77a1.22 1.22 0 0 0 1.071-1.803L18.954 2.642a1.22 1.22 0 0 0-2.137-.001z"
            class="clr-i-outline clr-i-outline-path-3"
          ></path>
          <path fill="none" d="M0 0h36v36H0z"></path>
        </svg>

        <h1>Erreur 404</h1>
        <p>La page que vous recherchez n'a pas été trouvée ou n'existe pas.</p>
        <RouterLink to="/" class="returnLink"> Retour </RouterLink>
      </section>
    </div>
  </main>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  text-align: center;
  min-height: 80vh;
}
.returnLink {
  display: block;
  font-size: 2em;
    color: var(--color-link);
  
}
.container * {
  margin: 30px 0;
}
</style>
