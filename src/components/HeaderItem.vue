<template>
  <!-- Main header that sticks to the top of the viewport - 'scrolled' class is dynamically added -->
  <header class="sticky-nav-bar container" :class="{ scrolled: isScrolled }">
    <RouterLink to="/" class="logo">
      <img src="../assets/img/logo-nyta.svg" alt="logo de NYTA, acronyme de Now You Take Action" />
    </RouterLink>

    <nav class="menu">
      <ul v-show="!isScrolled || isMenuOpen" class="menu__list">
        <li class="menu__item">
          <RouterLink
            to="/#presentation"
            @click="toggleMenu"
            :class="{ active: activeSection === 'presentation' }"
          >
            Présentation
          </RouterLink>
        </li>
        <li class="menu__item">
          <RouterLink
            to="/#creations"
            @click="toggleMenu"
            :class="{ active: activeSection === 'creations' }"
          >
            Portfolio
          </RouterLink>
        </li>
        <li class="menu__item">
          <RouterLink
            to="/#contact"
            @click="toggleMenu"
            :class="{ active: activeSection === 'contact' }"
          >
            Contact
          </RouterLink>
        </li>
        <li class="menu__dot"></li>
      </ul>

      <div class="menu__icons">
        <!-- Close icon when menu is open -->
        <svg
          @click="toggleMenu"
          v-if="isMenuOpen"
          class="menu-burger-icon"
          xmlns="http://www.w3.org/2000/svg"
          width="32"
          height="32"
          viewBox="0 0 24 24"
        >
          <g
            fill="none"
            stroke="var(--color-link)"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
          >
            <path d="M5 5L19 19M5 19L19 5" />
          </g>
        </svg>

        <!-- Burger menu icon to open menu when it is closed -->
        <svg
          @click="toggleMenu"
          v-else
          class="menu-burger-icon"
          xmlns="http://www.w3.org/2000/svg"
          width="32"
          height="32"
          viewBox="0 0 24 24"
        >
          <g
            fill="none"
            stroke="var(--color-link)"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
          >
            <path d="M3 6h18M3 12h18M3 18h18" />
          </g>
        </svg>

        <DarkModeToogle class="menu__switch-dark-mode" />
      </div>
    </nav>

    <!-- Mobile-only dropdown menu -->
    <div v-if="isMenuOpen" class="menu__dropdown">
      <ul>
        <li class="menu__drop-item">
          <RouterLink
            to="/#presentation"
            @click="toggleMenu"
            :class="{ active: activeSection === 'presentation' }"
            >Présentation</RouterLink
          >
        </li>
        <li class="menu__drop-item">
          <RouterLink
            to="/#creations"
            @click="toggleMenu"
            :class="{ active: activeSection === 'creations' }"
            >Portfolio</RouterLink
          >
        </li>
        <li class="menu__drop-item">
          <RouterLink
            to="/#contact"
            @click="toggleMenu"
            :class="{ active: activeSection === 'contact' }"
            >Contact</RouterLink
          >
        </li>
      </ul>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import DarkModeToogle from './DarkModeToogle.vue'

const isLargeScreen = ref(window.innerWidth >= 768)
const handleResize = () => {
  isLargeScreen.value = window.innerWidth >= 768
}
window.addEventListener('resize', handleResize)

// State management for scroll position and menu visibility
const isScrolled = ref(false)
const isMenuOpen = ref(false)
const activeSection = ref('')

const toggleMenu = () => {
  if (!isScrolled.value && isLargeScreen.value) {
    return
  }
  isMenuOpen.value = !isMenuOpen.value
}

// Update header state based on scroll position
const handleScroll = () => {
  isScrolled.value = window.scrollY > 80

  // Reset menu state when returning to top
  if (window.scrollY === 0) {
    isMenuOpen.value = false
  }
}

//Detect the active section
const updateActiveSection = () => {
  const sections = [
    { id: 'hero', route: '/' },
    { id: 'presentation', route: '/#presentation' },
    { id: 'creations', route: '/#creations' },
    { id: 'contact', route: '/#contact' },
  ]

  let currentSection = 'hero'

  for (const section of sections) {
    const element = document.getElementById(section.id)
    if (element) {
      const rect = element.getBoundingClientRect()
      if (rect.top <= window.innerHeight / 2 && rect.bottom >= window.innerHeight / 2) {
        currentSection = section.id
        break
      }
    }
  }

  // Update the active section without reloading the page
  if (window.location.pathname !== '/notFound') {
    activeSection.value = currentSection
    if (currentSection === 'hero') {
      window.history.pushState(null, '', '/')
    } else {
      window.history.pushState(null, '', `/#${currentSection}`)
    }
  }
}

onMounted(() => {
  window.addEventListener('scroll', updateActiveSection)
  window.addEventListener('scroll', handleScroll)
  window.addEventListener('resize', handleResize)
})

onUnmounted(() => {
  window.removeEventListener('scroll', updateActiveSection)
  window.removeEventListener('scroll', handleScroll)
  window.removeEventListener('resize', handleResize)
})
</script>

<style scoped>
.sticky-nav-bar {
  position: sticky;
  top: 0;
  z-index: 1000;
  height: 60px;
  background-color: var(--color-background);
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100vw;
}

.logo img {
  height: 50px;
  margin: 0px 20px;
}

.logo img:hover {
  height: 52px;
  box-shadow: 0px 2px 0px 0px var(--color-border);
  transition: all 0.2s ease-in-out;
}

.menu {
  display: flex;
}

.menu__list {
  display: flex;
  position: relative;
  flex-wrap: wrap;
  align-items: center;
  justify-content: flex-end;
}

.menu__item {
  padding: 0px 20px;
  transition: all 0.2s ease-in-out;
}
.menu__item a {
  text-decoration: none;
  color: var(--color-link);
  font-weight: 500;
  font-size: 1.1em;
  transition: all 0.2s ease-in-out;
}

.menu__item:hover {
  padding-bottom: 2px;
  transition: all 0.2s ease-in-out;
  color: var(--color-herotitle-text);
}

.menu__item .active {
  color: var(--color-border);
}
.menu__dot {
  position: absolute;
  z-index: 99;
  top: 28px;
  left: -3px;
  width: 40px;
  height: 3px;
  opacity: 0;
  background: var(--color-border);
  box-shadow: 0px 1px 2px 0px var(--color-border);
  border-radius: 0 0 50% 50%;
  transform: translateX(0px);
  transition: all 0.2s ease-in-out;
}

.menu__list li:nth-child(1):hover ~ .menu__dot {
  transform: translateX(60px);
  transition: all 0.2s ease-in-out;
  opacity: 1;
}

.menu__list li:nth-child(2):hover ~ .menu__dot {
  transform: translateX(195px);
  transition: all 0.2s ease-in-out;
  opacity: 1;
}

.menu__list li:nth-child(3):hover ~ .menu__dot {
  transform: translateX(310px);
  transition: all 0.2s ease-in-out;
  opacity: 1;
}

.menu__icons {
  display: flex;
  margin-right: 20px;
}

.menu-burger-icon {
  margin-right: 20px;
}
.menu-burger-icon:hover {
  opacity: 0.7;
}

.menu__switch-dark-mode:hover {
  cursor: pointer;
  opacity: 0.7;
  transition: all 0.2s ease-in-out;
}

/* Mobile dropdown menu */
.menu__dropdown {
  display: none;
  position: absolute;
  top: 60px;
  width: 100%;
  background-color: var(--color-background);
  box-shadow: 0px 4px 8px var(--color-shadow);
}

.menu__drop-item a:hover {
  transition: all 0.2s ease-in-out;
  color: var(--color-herotitle-text);
}
.menu__drop-item .active {
  color: var(--color-border);
}

/* Mobile viewport adaptations */
@media (max-width: 768px) {
  .menu__list {
    display: none;
  }

  .menu__icons {
    display: flex;
  }

  .menu__dropdown {
    display: flex;
    flex-wrap: wrap;
    align-items: flex-start;
    justify-content: center;
    text-align: center;
  }
  .menu__dropdown a {
    padding-top: 10px;
    padding-bottom: 10px;
  }
}

/* Desktop viewport adaptations */
@media (min-width: 768px) {
  .menu__dropdown {
    display: none;
  }

  .sticky-nav-bar:not(.scrolled) .menu__list {
    display: flex;
  }

  .sticky-nav-bar:not(.scrolled) .menu-burger-icon {
    display: none;
  }
}
</style>
