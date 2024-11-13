<template>
  <footer>
    <div class="container">
      <!-- Social media links (or other important links) -->
      <nav class="social">
        <ul class="social__list">
          <li class="social__item github">
            <a class="social__link" href="https://github.com/nytaneliah" target="_blank">
              <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24">
                <path
                  fill="var(--color-body-text)"
                  fill-rule="evenodd"
                  d="M11.999 1C5.926 1 1 5.925 1 12c0 4.86 3.152 8.983 7.523 10.437c.55.102.75-.238.75-.53c0-.26-.009-.952-.014-1.87c-3.06.664-3.706-1.475-3.706-1.475c-.5-1.27-1.221-1.61-1.221-1.61c-.999-.681.075-.668.075-.668c1.105.078 1.685 1.134 1.685 1.134c.981 1.68 2.575 1.195 3.202.914c.1-.71.384-1.195.698-1.47c-2.442-.278-5.01-1.222-5.01-5.437c0-1.2.428-2.183 1.132-2.952c-.114-.278-.491-1.397.108-2.91c0 0 .923-.297 3.025 1.127A10.5 10.5 0 0 1 12 6.32a10.5 10.5 0 0 1 2.754.37c2.1-1.424 3.022-1.128 3.022-1.128c.6 1.514.223 2.633.11 2.911c.705.769 1.13 1.751 1.13 2.952c0 4.226-2.572 5.156-5.022 5.428c.395.34.747 1.01.747 2.037c0 1.47-.014 2.657-.014 3.017c0 .295.199.637.756.53C19.851 20.979 23 16.859 23 12c0-6.075-4.926-11-11.001-11"
                />
              </svg>
            </a>
          </li>
          <li class="social__item linkedin">
            <a class="social__link" href="https://linkedin.com" target="_blank">
              <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 20 20">
                <path
                  fill="#0a66c2"
                  d="M10 .4C4.698.4.4 4.698.4 10s4.298 9.6 9.6 9.6s9.6-4.298 9.6-9.6S15.302.4 10 .4M7.65 13.979H5.706V7.723H7.65zm-.984-7.024c-.614 0-1.011-.435-1.011-.973c0-.549.409-.971 1.036-.971s1.011.422 1.023.971c0 .538-.396.973-1.048.973m8.084 7.024h-1.944v-3.467c0-.807-.282-1.355-.985-1.355c-.537 0-.856.371-.997.728c-.052.127-.065.307-.065.486v3.607H8.814v-4.26c0-.781-.025-1.434-.051-1.996h1.689l.089.869h.039c.256-.408.883-1.01 1.932-1.01c1.279 0 2.238.857 2.238 2.699z"
                />
              </svg>
            </a>
          </li>
        </ul>
      </nav>

      <!-- Copyright information -->
      <small>
        <div>&copy; 2024 NYTA</div>
        <div>mise à jour le <time datetime="2024-11-12">12 novembre 2024</time>.</div>
      </small>
    </div>
  </footer>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-bottom: 15px;
}

.social__list {
  display: flex;
  list-style: none;
  justify-content: center;
  padding-inline-start: 0;
}
.social__link {
  display: block;
  text-align: center;
  margin: 10px;
  border-radius: 50%;
}
.social__link:hover {
  position: relative;
  bottom: 4px;
  box-shadow: 2px 1px 2px 1px var(--color-border);
  transition: all 0.2s ease-in-out;
}
small {
  display: flex;
  justify-content: space-between;
  width: calc(100vw - 40px);
  * {
    font-size: 0.7rem;
  }
}
</style>
