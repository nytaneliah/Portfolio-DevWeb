<template>
  <main class="container">
    <section id="hero">
      <RouterLink to="#presentation">
        <div class="avatar__container">
          <img
            class="avatar__img"
            src="../assets/avatar.jpg"
            alt="Avatar de Nytaneliah Ranaivoson"
          />
          <div class="hero__text">
            <h2>Nytaneliah Ranaivoson</h2>
            <h1>Développeur Web</h1>
          </div>
        </div>
      </RouterLink>
    </section>

    <section id="presentation">
      <h2>Présentation</h2>

      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Commodi vitae repellat ex, iure
        placeat accusamus est obcaecati totam fugit nihil officiis nulla laborum nam, error
        necessitatibus, excepturi illum ut doloremque?
      </p>
    </section>
    <section id="creations">
      <h2>Mes créations</h2>
    </section>
    <section id="contact">
      <h2>Contactez-moi</h2>
    </section>
  </main>
</template>

<script setup></script>

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
  padding: 60px 15px 0 15px;
}

#hero {
  display: flex;
  align-items: center;
  justify-content: center;
  height: calc(100vh - 60px);
  width: calc(100% - 30px);
  padding: 60px 15px 15px 15px;
  margin-top: -60px;
  background-image: url('../assets/hero-bg.svg');
  background-position: bottom;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
}

.avatar__container {
  flex-shrink: 0;
  padding: 20px;
  background-color: var(--color-box-background);
  border: solid 10px var(--colox-box-border);
  border-radius: 15px;
  display: flex;
  align-items: center;
  transition: all 0.2s ease-in-out;
}

.avatar__container:hover {
  box-shadow: 0px 1px 10px 1px var(--color-border);
  transition: all 0.2s ease-in-out;
}

.avatar__img {
  border-radius: 50%;
  width: 150px;
  height: 150px;
}

.hero__text {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.hero__text h2 {
  font-size: clamp(1rem, 3vw, 2rem);
  margin: 0 0 10px 7px;
}

.hero__text h1 {
  font-size: clamp(1.5rem, 5vw, 3rem);
  margin: 0 0 0 5px;
}

#creations {
  background-image: url('../assets/hero-bg-2.svg');
  background-position: bottom;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
}
</style>
