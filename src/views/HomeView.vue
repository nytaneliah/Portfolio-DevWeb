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
        Qualité – Dans tous mes projets, je vise une rigueur professionnelle exemplaire. Lors de la
        rédaction d’un cahier des charges pour un site e-commerce, j’ai travaillé chaque détail pour
        répondre aux attentes des utilisateurs, assurant ainsi une base solide pour un développement
        efficace et structuré.
      </p>
      <p>
        Créativité – Le web est mon terrain d’expression. J’ai conçu mon CV et ce portfolio pour
        refléter une identité unique, dynamique et authentique, montrant que l’originalité peut
        aller de pair avec une navigation claire et intuitive.
      </p>
      <p>
        Design – L’esthétique doit avant tout servir l’expérience utilisateur. En dynamisant un
        espace de commentaires, j’ai travaillé à concevoir une interface soignée et ergonomique, où
        chaque interaction devient fluide et engageante, pour une utilisation optimale et agréable.
      </p>
      <p>
        Ces valeurs sont au cœur de ma démarche et de chacun des projets que je réalise. Découvrez
        mes créations ci-dessous et explorez comment qualité, créativité et design se traduisent
        dans mes réalisations.
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
  border: 10px solid var(--color-box-border);
  border-radius: 15px;
  display: flex;
  align-items: center;
  transition: all 0.2s ease-in-out;
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
