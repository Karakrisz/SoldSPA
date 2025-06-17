<script setup>
const onSubmit = () => {
  // Itt adhatsz hozzá valamilyen logikát a form elküldéséhez,
  // például POST kérést, vagy validációt.
  // Jelenleg csak konzolra írjuk:
  console.log('Űrlap elküldve.')
}
</script>
<template>
  <section class="contact">
    <div class="contact__inner">
      <!-- Bal oldali űrlap -->
      <div class="contact__form-wrapper">
        <h2 class="contact__title">KAPCSOLAT</h2>
        <form class="contact__form" @submit.prevent="onSubmit">
          <div class="contact__row">
            <div class="contact__field">
              <input
                type="text"
                id="name"
                name="name"
                class="contact__input"
                placeholder="Név"
                required
              />
            </div>
            <div class="contact__field">
              <input
                type="email"
                id="email"
                name="email"
                class="contact__input"
                placeholder="E-mail cím"
                required
              />
            </div>
          </div>

          <div class="contact__row">
            <div class="contact__field">
              <input
                type="tel"
                id="phone"
                name="phone"
                class="contact__input"
                placeholder="Telefonszám"
              />
            </div>
            <div class="contact__field">
              <input
                type="text"
                id="subject"
                name="subject"
                class="contact__input"
                placeholder="Tárgy"
              />
            </div>
          </div>

          <div class="contact__row">
            <div class="contact__field contact__field--full">
              <textarea
                id="message"
                name="message"
                class="contact__textarea"
                placeholder="Írd ide az üzeneted…"
                rows="9"
              ></textarea>
            </div>
          </div>

          <p class="contact__disclaimer">
            A küldés gombra kattintva elfogadja az
            <NuxtLink to="/" class="contact__disclaimer-link"
              >Adatvédelmi Tájékoztatót</NuxtLink
            >.
          </p>

          <button type="submit" class="contact__button">KÜLDÉS</button>
        </form>
      </div>

      <!-- Jobb oldali információs sáv -->
      <aside class="contact__aside">
        <h3 class="contact__aside-title">SOLDACH</h3>
        <nav class="contact__nav">
          <NuxtLink to="#rolunk" class="contact__nav-link">Rólunk</NuxtLink>
          <NuxtLink to="#szolgaltatasok" class="contact__nav-link"
            >Szolgáltatások</NuxtLink
          >
          <NuxtLink to="#blog" class="contact__nav-link">Blog</NuxtLink>
          <NuxtLink to="#kapcsolat" class="contact__nav-link"
            >Kapcsolat</NuxtLink
          >
        </nav>

        <hr class="contact__divider" />

        <div class="contact__info">
          <p class="contact__info-phone">06 20 12 34 567</p>
          <p class="contact__info-email">soldach@gmail.com</p>
        </div>

        <hr class="contact__divider" />

        <div class="contact__logo-wrapper">
          <!-- Itt a Digital Seed Studio logója, cseréld a src-t a saját logódra -->
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="88"
            height="36"
            viewBox="0 0 88 36"
            fill="none"
          >
            <g opacity="0.4" clip-path="url(#clip0_69_155)">
              <path
                d="M42.3024 3.79639H45.219C47.9533 3.79639 49.8901 5.39222 49.8901 7.65112C49.8901 9.91002 47.9533 11.5171 45.219 11.5171H42.3024V3.79639ZM45.5836 9.53916C46.7684 9.53916 47.6115 8.75247 47.6115 7.65112C47.6115 6.54977 46.7684 5.77433 45.5836 5.77433H44.5126V9.53916H45.5836Z"
                fill="white"
              />
              <path
                d="M51.0067 3.79639H53.217V11.5171H51.0067V3.79639Z"
                fill="white"
              />
              <path
                d="M58.2071 6.99939H61.8756V10.281C61.0667 11.1463 59.8704 11.652 58.64 11.652C56.293 11.652 54.322 9.82021 54.322 7.65122C54.322 5.48222 56.293 3.66162 58.64 3.66162C59.8704 3.66162 61.0667 4.16734 61.8756 5.02145L60.2464 6.42624C59.8591 5.93176 59.2666 5.63956 58.64 5.63956C57.5349 5.63956 56.6006 6.5611 56.6006 7.65122C56.6006 8.74133 57.5349 9.67411 58.64 9.67411C59.0274 9.67411 59.4033 9.56173 59.7337 9.35944V8.60647H58.2071V6.99939Z"
                fill="white"
              />
              <path
                d="M63.1061 3.79639H65.3163V11.5171H63.1061V3.79639Z"
                fill="white"
              />
              <path
                d="M68.6089 5.74061H66.2961V3.79639H73.132V5.74061H70.8192V11.5171H68.6089V5.74061Z"
                fill="white"
              />
              <path
                d="M78.5551 10.4832H75.8322L75.4334 11.5171H72.9384L75.9461 3.79639H78.4412L81.449 11.5171H78.9539L78.5551 10.4832ZM77.9285 8.8761L77.1994 6.9993L76.4588 8.8761H77.9285Z"
                fill="white"
              />
              <path
                d="M88 9.57287V11.5171H82.1439V3.79639H84.3542V9.57287H88Z"
                fill="white"
              />
              <path
                d="M41.71 20.7195L42.9404 19.2698C43.7379 19.8879 44.6038 20.2138 45.5266 20.2138C46.1305 20.2138 46.4495 20.0115 46.4495 19.6743C46.4495 19.3035 46.176 19.2473 45.0937 19C43.3961 18.6179 42.0859 18.1796 42.0859 16.5726C42.0859 14.9655 43.3164 14.0327 45.1734 14.0327C46.5292 14.0327 47.5888 14.3923 48.4547 15.0779L47.3495 16.6175C46.6204 16.1006 45.8229 15.8421 45.1165 15.8421C44.581 15.8421 44.319 16.0556 44.319 16.3478C44.319 16.7411 44.5924 16.8648 45.7089 17.1008C47.5318 17.4829 48.6711 17.9661 48.6711 19.4383C48.6711 21.0679 47.4065 22.0231 45.4469 22.0231C44.0341 22.0231 42.7012 21.5848 41.71 20.7195Z"
                fill="white"
              />
              <path
                d="M51.8726 16.1117V16.9771H55.5981V18.9213H51.8726V19.944H55.9627V21.8882H49.6624V14.1675H55.9627V16.1117H51.8726Z"
                fill="white"
              />
              <path
                d="M59.2895 16.1117V16.9771H63.015V18.9213H59.2895V19.944H63.3796V21.8882H57.0792V14.1675H63.3796V16.1117H59.2895Z"
                fill="white"
              />
              <path
                d="M64.4961 14.1675H67.4127C70.147 14.1675 72.0839 15.7633 72.0839 18.0222C72.0839 20.2811 70.147 21.8882 67.4127 21.8882H64.4961V14.1675ZM67.7773 19.9102C68.9622 19.9102 69.8053 19.1236 69.8053 18.0222C69.8053 16.9209 68.9622 16.1454 67.7773 16.1454H66.7063V19.9102H67.7773Z"
                fill="white"
              />
              <path
                d="M41.71 31.0344L42.9404 29.5847C43.7379 30.2028 44.6038 30.5287 45.5266 30.5287C46.1305 30.5287 46.4495 30.3264 46.4495 29.9893C46.4495 29.6184 46.176 29.5622 45.0937 29.315C43.3961 28.9329 42.0859 28.4946 42.0859 26.8875C42.0859 25.2804 43.3164 24.3477 45.1734 24.3477C46.5292 24.3477 47.5888 24.7073 48.4547 25.3928L47.3495 26.9325C46.6204 26.4155 45.8229 26.157 45.1165 26.157C44.581 26.157 44.319 26.3705 44.319 26.6627C44.319 27.0561 44.5924 27.1797 45.7089 27.4157C47.5318 27.7978 48.6711 28.2811 48.6711 29.7533C48.6711 31.3828 47.4065 32.3381 45.4469 32.3381C44.0341 32.3381 42.7012 31.8998 41.71 31.0344Z"
                fill="white"
              />
              <path
                d="M51.5535 26.4266H49.2407V24.4824H56.0766V26.4266H53.7638V32.2031H51.5535V26.4266Z"
                fill="white"
              />
              <path
                d="M56.9425 28.7754V24.4824H59.1528V28.6631C59.1528 29.652 59.7794 30.36 60.668 30.36C61.5567 30.36 62.1833 29.652 62.1833 28.6631V24.4824H64.3936V28.7754C64.3936 30.8658 62.8555 32.338 60.668 32.338C58.4806 32.338 56.9425 30.8658 56.9425 28.7754Z"
                fill="white"
              />
              <path
                d="M65.6809 24.4824H68.5975C71.3319 24.4824 73.2687 26.0783 73.2687 28.3372C73.2687 30.5961 71.3319 32.2031 68.5975 32.2031H65.6809V24.4824ZM68.9621 30.2252C70.147 30.2252 70.9901 29.4385 70.9901 28.3372C70.9901 27.2358 70.147 26.4604 68.9621 26.4604H67.8912V30.2252H68.9621Z"
                fill="white"
              />
              <path
                d="M74.3853 24.4824H76.5955V32.2031H74.3853V24.4824Z"
                fill="white"
              />
              <path
                d="M77.7007 28.3372C77.7007 26.1683 79.6489 24.3477 81.9617 24.3477C84.2745 24.3477 86.2227 26.1683 86.2227 28.3372C86.2227 30.5062 84.2745 32.3381 81.9617 32.3381C79.6489 32.3381 77.7007 30.5062 77.7007 28.3372ZM83.9441 28.3372C83.9441 27.2471 83.0326 26.3256 81.9617 26.3256C80.8907 26.3256 79.9793 27.2471 79.9793 28.3372C79.9793 29.4274 80.8907 30.3601 81.9617 30.3601C83.0326 30.3601 83.9441 29.4386 83.9441 28.3372Z"
                fill="white"
              />
              <path
                d="M27.3604 8.20039C25.8774 8.20039 24.4096 8.47573 23.0387 9.01891C21.6696 9.56022 20.424 10.3544 19.3758 11.3565L18.9884 11.7273L18.9011 11.201C18.4435 8.46262 16.9795 5.96959 14.773 4.16772C12.5646 2.36584 9.75626 1.375 6.85293 1.375H0V6.21496C0 9.30549 1.28362 12.2724 3.56983 14.462C5.85793 16.6516 8.96254 17.8822 12.2001 17.8822H16.0509V29.4127C14.8641 29.9671 14.0419 31.1583 14.0419 32.5388C14.0419 34.4512 15.6142 36.0021 17.5529 36.0021C19.4916 36.0021 21.0639 34.4512 21.0639 32.5388C21.0639 31.1565 20.2417 29.9671 19.053 29.4127V23.0012H23.7944C26.7965 23.0012 29.6732 21.8605 31.7942 19.832C33.9133 17.8035 35.1039 15.0539 35.1039 12.19V8.20226H27.3623L27.3604 8.20039ZM15.768 15.0258H12.202C9.76385 15.0258 7.42448 14.0986 5.70033 12.4485C3.97428 10.7964 3.00207 8.5544 3.00207 6.21496V4.22953H6.85293C9.29104 4.22953 11.6304 5.15669 13.3565 6.80684C15.0825 8.45887 16.0547 10.7009 16.0547 13.0403V15.0258H15.7718H15.768ZM32.1018 11.334V12.1881C32.1018 14.3009 31.2246 16.3275 29.6656 17.8185C28.1067 19.3094 25.9952 20.1467 23.7944 20.1467H19.053V19.0135C19.053 16.9007 19.9303 14.8741 21.4892 13.3831C23.0482 11.8922 25.1597 11.0549 27.3604 11.0549H32.1018V11.334Z"
                fill="white"
              />
              <path
                d="M16.1136 2.56608C16.2142 2.64849 16.3073 2.73465 16.406 2.81894C16.7839 2.78897 17.1655 2.77024 17.5529 2.77024C21.098 2.77024 24.3489 4.03642 26.8667 6.13236C27.0262 6.12674 27.1857 6.12112 27.3471 6.12112H30.8125C27.6434 2.38065 22.8792 0 17.551 0C15.9598 0 14.4217 0.217274 12.9596 0.612487C14.0875 1.12383 15.1509 1.77752 16.1136 2.5642V2.56608Z"
                fill="white"
              />
              <path
                d="M33.2602 21.3209C32.4323 22.1132 31.5132 22.7875 30.5296 23.3381C28.9536 26.483 26.2364 28.976 22.9153 30.289C23.2134 30.9802 23.3786 31.7406 23.3786 32.5386C23.3786 32.7259 23.3691 32.9113 23.3501 33.093C29.1796 31.0439 33.5659 25.9922 34.5951 19.8262C34.1925 20.3544 33.7463 20.8563 33.2602 21.3209Z"
                fill="white"
              />
              <path
                d="M3.08561 17.039C3.08561 16.9622 3.08941 16.8873 3.09131 16.8105C2.75141 16.5389 2.42102 16.2542 2.10391 15.9508C1.52286 15.3945 0.998782 14.7895 0.529768 14.1489C0.366467 15.0892 0.277222 16.0538 0.277222 17.039C0.277222 24.4432 5.06611 30.7404 11.7519 33.0911C11.7348 32.9075 11.7235 32.724 11.7235 32.5366C11.7235 31.7387 11.8886 30.9783 12.1868 30.2871C6.85861 28.1799 3.08371 23.0384 3.08371 17.039H3.08561Z"
                fill="white"
              />
            </g>
            <defs>
              <clipPath id="clip0_69_155">
                <rect width="88" height="36" fill="white" />
              </clipPath>
            </defs>
          </svg>
        </div>
      </aside>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use 'sass:color';
.contact {
  background-color: #ffffff;
  position: relative;

  .contact__input::-webkit-input-placeholder,
  .contact__textarea::-webkit-input-placeholder {
    color: #d1d1d1;
  }

  &__inner {
    max-width: 1200px;
    display: flex;
    position: absolute;
    top: -20em;
    left: 0;
    right: 0;
    margin: auto;
    width: 84%;

    @media (max-width: 768px) {
      flex-direction: column;
    }
  }

  // ╔══════════════════════════════╗
  // ║  Bal oldali űrlap („form-wrapper”)   ║
  // ╚══════════════════════════════╝
  &__form-wrapper {
    flex: 1 1 600px;
    background-color: #1a1a1a;
    padding: 2em 3em 3em 3em;
    color: #ffffff;

    @media (max-width: 768px) {
      padding: 1.5rem;
    }
  }

  &__title {
    font-size: 2rem;
    font-weight: 700;
    margin: 0.5em 0 1em 0;
    color: #ffffff;
  }

  &__form {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  &__row {
    display: flex;
    gap: 1rem;

    @media (max-width: 768px) {
      flex-direction: column;
      gap: 0.75rem;
    }
  }

  &__field {
    flex: 1;
    display: flex;
    flex-direction: column;

    &--full {
      flex: 1 1 100%;
    }
  }

  &__label {
    font-size: 0.875rem;
    margin-bottom: 0.5rem;
    color: #e0e0e0;
  }

  &__input,
  &__textarea {
    background-color: #ffffff;
    color: #333333;
    border: none;
    border-radius: 39px;
    padding: 1em 2em;
    font-size: 1rem;
    line-height: 1.4;
    outline: none;
    resize: none; // a textarea-t ne lehessen méretezni

    &::placeholder {
      color: #aaaaaa;
    }

    &:focus {
      box-shadow: 0 0 0 3px rgba(245, 166, 35, 0.5);
    }
  }

  &__textarea {
    min-height: 150px;
  }

  &__disclaimer {
    font-size: 1rem;
    color: #525252;
    text-align: center;
  }

  &__disclaimer-link {
    color: #f5a623;
    text-decoration: underline;
    transition: color 0.2s ease;

    &:hover,
    &:focus {
      color: color.adjust(#f5a623, $lightness: -10%);
    }
  }

  &__button {
    align-self: center;
    background-color: #f5a623;
    color: #ffffff;
    border: none;
    border-radius: 34px;
    padding: 10px 24px;
    font-size: 1rem;
    font-weight: 700;
    text-transform: uppercase;
    cursor: pointer;
    transition: background-color 0.2s ease;

    &:hover,
    &:focus {
      background-color: color.adjust(#f5a623, $lightness: -10%);
    }
  }

  // ╔══════════════════════════════╗
  // ║  Jobb oldali „aside” blokk         ║
  // ╚══════════════════════════════╝
  &__aside {
    flex: 0 0 350px;
    background-color: #f4a32a;
    padding: 2rem 1.5rem;
    color: #ffffff;
    display: flex;
    flex-direction: column;
    align-items: center;

    @media (max-width: 1024px) {
      flex: 1 1 auto;
    }

    @media (max-width: 768px) {
      margin-top: 1.5rem;
    }
  }

  &__aside-title {
    font-size: 1.75rem;
    font-weight: 700;
    margin: 1em 0 .7em -1em;
    text-transform: uppercase;
    color: #ffffff;
  }

  &__nav {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
    width: 40%;
    margin: 1em 1em 2em 1em;
  }

  &__nav-link {
    font-size: 1rem;
    color: #ffffff;
    text-decoration: none;
    transition: color 0.2s ease;

    &:hover,
    &:focus {
      color: color.adjust(#ffffff, $lightness: -20%);
    }
  }

  &__divider {
    width: 100%;
    border: none;
    border-top: 1px solid rgba(255, 255, 255, 0.4);
    margin: 1rem 0;
  }

  &__info {
    display: flex;
    flex-direction: column;
    gap: 0.25rem;
    margin: 1.5em 1em 1.5em 1em;
  }

  &__info-phone,
  &__info-email {
    font-size: 1rem;
    color: #ffffff;
    margin: 0;
  }

  &__logo-wrapper {
    margin-top: 33%;
  }

  &__logo {
    display: block;
    width: 100%;
    max-width: 120px;
    height: auto;
    object-fit: contain;
  }
}
</style>
