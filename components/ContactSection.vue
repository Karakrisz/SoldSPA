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
              <label for="name" class="contact__label">Név*</label>
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
              <label for="email" class="contact__label">E-mail cím*</label>
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
              <label for="phone" class="contact__label">Telefonszám</label>
              <input
                type="tel"
                id="phone"
                name="phone"
                class="contact__input"
                placeholder="Telefonszám"
              />
            </div>
            <div class="contact__field">
              <label for="subject" class="contact__label">Tárgy</label>
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
              <label for="message" class="contact__label">Üzenet</label>
              <textarea
                id="message"
                name="message"
                class="contact__textarea"
                placeholder="Írd ide az üzeneted…"
                rows="6"
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
          <NuxtImg
            src="/img/test.png"
            alt="Digital Seed Studio logo"
            class="contact__logo"
          />
        </div>
      </aside>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use 'sass:color';
.contact {
  background-color: #ffffff;
  padding: 2rem 1rem;

  &__inner {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    gap: 2rem;

    @media (max-width: 768px) {
      flex-direction: column;
    }
  }

  // ╔══════════════════════════════╗
  // ║  Bal oldali űrlap („form-wrapper”)   ║
  // ╚══════════════════════════════╝
  &__form-wrapper {
    flex: 1 1 600px;
    background-color: #191919;
    padding: 2rem;
    border-radius: 4px;
    color: #ffffff;

    @media (max-width: 768px) {
      padding: 1.5rem;
    }
  }

  &__title {
    font-size: 2rem;
    font-weight: 700;
    margin-bottom: 1.5rem;
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
    border-radius: 24px;
    padding: 0.75rem 1rem;
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
    font-size: 0.75rem;
    color: #707070;
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
    border-radius: 999px;
    padding: 0.75rem 2rem;
    font-size: 1rem;
    font-weight: 600;
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
    flex: 0 0 300px;
    background-color: #f5a623;
    border-radius: 4px;
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
    margin-bottom: 1.5rem;
    text-transform: uppercase;
    color: #ffffff;
  }

  &__nav {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
    margin-bottom: 1.5rem;
    width: 100%;
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
    margin-bottom: 1.5rem;
    text-align: center;
  }

  &__info-phone,
  &__info-email {
    font-size: 1rem;
    color: #ffffff;
    margin: 0;
  }

  &__logo-wrapper {
    margin-top: auto;
    /* Alulra tolja a logót */
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
