<script setup>
import HomeHero from '../components/HomeHero.vue'
import HomePresentation from '../components/HomePresentation.vue'
import HomeCreations from '../components/HomeCreations.vue'
import HomeContact from '../components/HomeContact.vue'
</script>

<template>
  <main class="container">
    <HomeHero />
    <HomePresentation />
    <HomeCreations />
    <HomeContact />


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
  flex: 1;
  width: 100%;
}

section {
  height: calc(100vh - 75px);
  width: 100%;
  padding-top: 60px;
}
</style>
