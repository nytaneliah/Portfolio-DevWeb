<script setup>
import HomeHero from '../components/HomeHero.vue'
import HomePresentation from '../components/HomePresentation.vue'
</script>

<template>
  <main class="container">
    <HomeHero />
    <HomePresentation />

    <section id="creations">
      <h2>Mes créations</h2>
    </section>
    <section id="contact">
      <h2>Contactez-moi</h2>
      <p>Donner vie à vos idées numériques</p>
    </section>
  </main>
</template>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  text-align: center;
  min-height: calc(100vh - 60px);
}

section {
  height: calc(100vh - 75px);
  width: 100%;
  padding-top: 60px;
}

#creations {
  background-image: url('../assets/img/hero-bg-2.svg');
  background-position: bottom;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
}
</style>
