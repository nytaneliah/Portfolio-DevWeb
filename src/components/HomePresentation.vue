<template>
  <section id="presentation">
    <h2>From Concept to Digital Reality</h2>
    <div class="presentation__block">
      <!-- Animated image for Quality -->
      <img
        src="../assets/img/img-qualite.gif"
        alt="Animated image of an engineer in a blue suit and yellow tie, wearing a yellow construction helmet, writing on a sheet, with a whiteboard on the right showing diagrams, a dollar sign, gears, a light bulb, and an upward arrow graph"
        class="presentation__img"
      />
      <div class="presentation__text">
        <h3>Quality</h3>
        <p>
          In all my projects, I aim for exemplary professional rigor. When drafting a specification
          for an e-commerce site, I work on every detail to meet user expectations, thus ensuring a
          solid foundation for efficient and structured development.
        </p>
      </div>
    </div>
    <div class="presentation__block">
      <!-- Animated image for Creativity -->
      <img
        src="../assets/img/img-creativite.gif"
        alt="Animated image of a rounded robot shaped like a smiling screen in front of a browser page with animated rectangle graphic elements in front of the page"
        class="presentation__img"
      />
      <div class="presentation__text">
        <h3>Creativity</h3>
        <p>
          The web is my playground. I designed my resume and this portfolio to reflect a unique,
          dynamic, and authentic identity, showing that originality can go hand in hand with clear
          and intuitive navigation.
        </p>
      </div>
    </div>
    <div class="presentation__block">
      <!-- Animated image for Design -->
      <img
        src="../assets/img/img-design.gif"
        alt="Animated image of a colorful web page where graphic elements are moved by a mouse cursor"
        class="presentation__img"
      />
      <div class="presentation__text">
        <h3>Design</h3>
        <p>
          Aesthetics should primarily serve the user experience. By energizing a comment section, I
          work on designing a neat and ergonomic interface where every interaction becomes smooth
          and engaging, for optimal and pleasant use.
        </p>
      </div>
    </div>
    <div class="presentation__block">
      <!-- Animated image for Sharing -->
      <img
        src="../assets/img/img-partage.gif"
        alt="Animated image of a man and woman in front of a large browser window, the man crouching on the left drawing a circle on the window with his finger, and the woman standing on the right holding a navigation bar that she is placing at the top of the page"
        class="presentation__img"
      />
      <div class="presentation__text">
        <p>
          These values are at the heart of my approach and every project I undertake. Discover my
          creations below and see how quality, creativity, and design translate into my work.
        </p>
      </div>
    </div>
    <RouterLink to="#creations">
      <!-- Animated down arrow for navigation -->
      <img
        class="link__image"
        src="../assets/img/img-cta-arrow.gif"
        alt="Animated arrows pointing downwards"
      />
    </RouterLink>
  </section>
</template>

<script setup></script>

<style scoped>
/* Main presentation section styles */
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

/* Style for presentation blocks */
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
