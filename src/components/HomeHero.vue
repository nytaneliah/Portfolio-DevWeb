<template>
  <section id="hero">
    <RouterLink to="#presentation">
      <div class="avatar__container">
        <img
          class="avatar__img"
          src="../assets/img/avatar.jpg"
          alt="Avatar de Nytaneliah Ranaivoson"
        />
        <div class="hero__text">
          <h1>Développeur Web</h1>
          <h2>Nytaneliah Ranaivoson</h2>
        </div>
      </div>
    </RouterLink>
  </section>
</template>
<script setup></script>
<style>
#hero {
  display: flex;
  align-items: center;
  justify-content: center;
  height: calc(100vh - 60px);
  width: calc(100% - 30px);
  padding: 60px 15px 15px 15px;
  margin-top: -60px;
  background-image: url('../assets/img/hero-bg.svg');
  background-position: bottom;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
}

.avatar__container {
  flex-shrink: 0;
  padding: 20px;
  background-color: var(--color-box-background);
  border: 10px solid var(--color-box-border);
  border-radius: 15px;
  display: flex;
  align-items: center;
  transition: all 0.2s ease-in-out;
}
@media (max-width: 570px) {
  .avatar__container {
    flex-wrap: wrap;
    justify-content: center;
  }
}

.avatar__container:hover {
  box-shadow: 0px 1px 10px 1px var(--color-border);
  transition: all 0.2s ease-in-out;
  background-color: var(--color-box-background-a);
  border: 10px solid var(--color-box-border-a);
}

.avatar__img {
  border-radius: 50%;
  width: 150px;
  height: 150px;
}

.hero__text {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.hero__text h2 {
  margin: 0 0 10px 7px;
}

.hero__text h1 {
  font-size: clamp(1.5rem, 5vw, 3rem);
  margin: 0 0 0 5px;
  order: 1;
}
</style>
