<script setup>
import HeaderItem from './components/HeaderItem.vue'
import FooterItem from './components/FooterItem.vue'
import { RouterView } from 'vue-router';
</script>

<template>
  <HeaderItem />

  <RouterView />

  <FooterItem />
</template>

<style scoped>

</style>
