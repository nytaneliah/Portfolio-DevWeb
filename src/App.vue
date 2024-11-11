<script setup>
import HeaderItem from './components/HeaderItem.vue'
import FooterItem from './components/FooterItem.vue'
import ToTheTopButton from './components/ToTheTopButton.vue';
import { RouterView } from 'vue-router';

</script>

<template>
  <ToTheTopButton />
  <HeaderItem />

  <RouterView />

  <FooterItem />
</template>

<style scoped>

</style>
