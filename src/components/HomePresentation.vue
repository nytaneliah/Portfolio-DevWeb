<template>
  <section id="presentation">
    <h2>Du concept à la réalité digitale</h2>
    <div class="presentation__block">
      <img
        src="../assets/img/img-qualite.gif"
        alt="image animée d'un ingénieur en costume bleu et cravate jaune, portant un casque de chantier jaune, il écrit sur une feuille, à droite il y a un tableau blanc avec des des schémas dessinés, un signe dollar, des engrenages, une ampoule, un graphique en flèche croissante"
        class="presentation__img"
      />
      <div class="presentation__text">
        <h3>Qualité</h3>
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
        alt="image animée d'un robot arrondi en forme d'écran souriant devant une page de navigateur avec des éléments graphiques rectangle animés devant la page"
        class="presentation__img"
      />
      <div class="presentation__text">
        <h3>Créativité</h3>
        <p>
          Le web est mon terrain d’expression. J’ai conçu mon CV et ce portfolio pour refléter une
          identité unique, dynamique et authentique, montrant que l’originalité peut aller de pair
          avec une navigation claire et intuitive.
        </p>
      </div>
    </div>
    <div class="presentation__block">
      <img
        src="../assets/img/img-design.gif"
        alt="image animée d'une page web colorée où les éléments graphiques sont déplacés par un curseur de souris "
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
        alt="image animée d'un homme et une femme devant une grande fenêtre denavigateur, l'homme accroupi à gauche dessine un cercle sur la fenêtre avec son doigt, la femme debout à droite porte une barre de navigation qu'elle pose au haut de la page"
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
        alt="flèches animées pointant vers le bas"
      />
    </RouterLink>
  </section>
</template>

<script setup></script>

<style scoped>
#presentation {
  min-height: 90vh;
  max-width: 90vw;
  display: flex;
  height: auto;
  flex-flow: column wrap;
  align-items: center;
  justify-content: center;
  margin: 10px 20px;
  gap: 5vh 10vw;
}
#presentation h2 {
  width: 100%;
}
@media (min-width: 768px) {
  #presentation > div:nth-child(odd) > img {
    order: 1;
  }
}

.link__image {
  max-height: 250px;
}

h3 {
  text-align: center;
}
.presentation__block {
  max-width: 800px;
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
  gap: 2vh 4vw;
}
.presentation__img {
  height: 100%;
  width: 100%;
  object-fit: contain;
  max-width: 245.5px;
}
.presentation__text {
  width: 60%;
  text-align: justify;
}
</style>
