<template>
  <header>
    <div class="container">
      <RouterLink to="/">
        <div class="logo">
          <img src="../assets/logo-nyta.svg" alt="logo de NYTA, acronyme de Now You Take Action" />
        </div>
      </RouterLink>
      <!-- Navigation menu with anchor links -->
      <nav class="menu">
        <ul class="menu__list">
          <li class="menu__item"><a href="#presentation">Présentation</a></li>
          <li class="menu__item"><a href="#creations">Créations</a></li>
          <li class="menu__item"><a href="#contact">Contact</a></li>
          <div class="dot"></div>
          <DarkModeToogle />
        </ul>
      </nav>
    </div>
  </header>
</template>

<script setup>
import DarkModeToogle from './DarkModeToogle.vue'
</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 60px;

}

.logo img {
  height: 50px;
}
.logo img:hover {
  height: 52px;
  box-shadow: 0px 2px 0px 0px var(--color-border);
  transition: all 0.2s ease-in-out;
}

.switch-dark-mode:hover {
  cursor: pointer;
  box-shadow: 0px 2px 2px 0px var(--color-border);
  border-radius: 50%;
  transition: all 0.2s ease-in-out;
}
.menu__list {
  list-style: none;
  position: relative;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: flex-end;
  padding-inline-start: 0;
}
.menu__item {
  color: var(--color-link);

  * {
    text-decoration: none;
    color: inherit;
    font-weight: 500;
    font-size: 1.1em;
    margin: 0 20px;
  }
}
.menu__item:hover {
  position: relative;
  bottom: 1px;
  transition: all 0.2s ease-in-out;
  color: var(--color-herotitle-text);
}

.dot {
  position: absolute;
  top: 28px;
  left: -3px;
  width: 40px;
  height: 3px;
  background: var(--color-border);
  box-shadow: 0px 1px 2px 0px var(--color-border);
  border-radius: 0 0 50% 50%;
  opacity: 0;
  -webkit-transform: translateX(0px);
  transform: translateX(0px);
  -webkit-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
}

.menu__list li:nth-child(1):hover ~ .dot {
  -webkit-transform: translateX(59px);
  transform: translateX(59px);
  -webkit-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  opacity: 1;
}

.menu__list li:nth-child(2):hover ~ .dot {
  -webkit-transform: translateX(200px);
  transform: translateX(200px);
  -webkit-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  opacity: 1;
}

.menu__list li:nth-child(3):hover ~ .dot {
  -webkit-transform: translateX(318px);
  transform: translateX(318px);
  -webkit-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  opacity: 1;
}

@media (min-width: 640px) {
}
</style>
