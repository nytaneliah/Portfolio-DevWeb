<template>
  <section id="presentation">
    <h2>From Concept to Digital Reality</h2>
    <div class="presentation__block">
      <img
        src="../assets/img/img-qualite.gif"
        alt="Image animée d'un ingénieur en costume bleu et cravate jaune, portant un casque de chantier jaune, écrivant sur une feuille, avec un tableau blanc à droite montrant des schémas, un signe dollar, des engrenages, une ampoule et un graphique en flèche montante"
        class="presentation__img"
      />
      <div class="presentation__text">
        <h3>Quality</h3>
        <p>
          Dans tous mes projets, je vise une rigueur professionnelle exemplaire. Lors de la
          rédaction d’un cahier des charges pour un site e-commerce, je travaille chaque détail pour
          répondre aux attentes des utilisateurs, assurant ainsi une base solide pour un
          développement efficace et structuré.
        </p>
      </div>
    </div>
    <div class="presentation__block">
      <img
        src="../assets/img/img-creativite.gif"
        alt="Image animée d'un robot arrondi en forme d'écran souriant devant une page de navigateur avec des éléments graphiques rectangulaires animés devant la page"
        class="presentation__img"
      />
      <div class="presentation__text">
        <h3>Creativity</h3>
        <p>
          Le web est mon terrain de jeu. J’ai conçu mon CV et ce portfolio pour refléter une
          identité unique, dynamique et authentique, montrant que l’originalité peut aller de pair
          avec une navigation claire et intuitive.
        </p>
      </div>
    </div>
    <div class="presentation__block">
      <img
        src="../assets/img/img-design.gif"
        alt="Image animée d'une page web colorée où les éléments graphiques sont déplacés par un curseur de souris"
        class="presentation__img"
      />
      <div class="presentation__text">
        <h3>Design</h3>
        <p>
          L’esthétique doit avant tout servir l’expérience utilisateur. En dynamisant un espace de
          commentaires, je travaille à concevoir une interface soignée et ergonomique, où chaque
          interaction devient fluide et engageante, pour une utilisation optimale et agréable.
        </p>
      </div>
    </div>
    <div class="presentation__block">
      <img
        src="../assets/img/img-partage.gif"
        alt="Image animée d'un homme et d'une femme devant une grande fenêtre de navigateur, l'homme accroupi à gauche dessinant un cercle sur la fenêtre avec son doigt, et la femme debout à droite tenant une barre de navigation qu'elle place en haut de la page"
        class="presentation__img"
      />
      <div class="presentation__text">
        <p>
          Ces valeurs sont au cœur de ma démarche et de chacun des projets que je réalise. Découvrez
          mes créations ci-dessous et comment qualité, créativité et design se traduisent dans mes
          réalisations.
        </p>
      </div>
    </div>
    <RouterLink to="#creations">
      <img
        class="link__image"
        src="../assets/img/img-cta-arrow.gif"
        alt="Flèches animées pointant vers le bas"
      />
    </RouterLink>
  </section>
</template>

<script setup></script>

<style scoped>
#presentation {
  max-width: 90vw;
  height: auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: 10px 20px;
  gap: 5vh 10vw;
}

.presentation__block {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 800px;
  gap: 20px;
  text-align: center;
}

.presentation__img {
  max-width: 300px;
  width: 100%;
  object-fit: contain;
}

.presentation__text {
  max-width: 500px;
  text-align: justify;
  margin: 0 auto;
}

/* Configuration for larger screens */
@media (min-width: 768px) {
  #presentation {
    flex-direction: column;
  }

  .presentation__block {
    flex-direction: row; /* Align blocks horizontally on larger screens */
    align-items: center;
    justify-content: space-between;
    gap: 30px;
  }

  /* Alternate the order of images for odd elements */
  .presentation__block:nth-child(odd) .presentation__img {
    order: 1;
  }

  .presentation__img {
    max-width: 300px;
    width: 45%;
  }

  .presentation__text {
    width: 55%;
  }
}

.link__image {
  max-height: 30vh;
  margin-bottom: 50px;
  align-self: center;
}

h3 {
  text-align: center;
}
</style>
