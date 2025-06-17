<template>
  <section class="blog">
    <div class="blog__inner">
      <h2 class="blog__title">BLOG</h2>

      <div class="blog__cards">
        <!-- 1. kártya -->
        <article class="blog__card">
          <div class="blog__card-image">
            <NuxtImg
              src="/img/test.png"
              alt="Modern, stílusos nappali sárga fotellel"
            />
          </div>
          <div class="blog__card-content">
            <h3 class="blog__card-title">
              MIBŐL TUDHATOD, HOGY IDEJE FELÚJÍTANI AZ OTTHONOD?
            </h3>
            <p class="blog__card-text">
              Fedezd fel, milyen jelek utalnak arra, hogy itt az ideje belevágni
              egy lakásfelújításba, mielőtt komolyabb problémák jelentkeznek.
            </p>
            <NuxtLink
              to="#"
              class="blog__card-button"
              aria-label="Tovább olvasok: Miből tudhatod..."
            >
              TOVÁBB OLVASOK
            </NuxtLink>
          </div>
        </article>

        <!-- 2. kártya -->
        <article class="blog__card">
          <div class="blog__card-image">
            <NuxtImg src="/img/test.png" alt="Vörös téglafal közelről" />
          </div>
          <div class="blog__card-content">
            <h3 class="blog__card-title">
              GIPSZKARTON VAGY TÉGLA? TÉRVÁLASZTÁS ÚJ SZINTEN
            </h3>
            <p class="blog__card-text">
              Összehasonlítjuk a gipszkartont és a tégla előnyeit, hogy
              segítsünk megtalálni a legjobb megoldást otthonod belső falainak
              kialakításához.
            </p>
            <NuxtLink
              to="#"
              class="blog__card-button"
              aria-label="Tovább olvasok: Gipszkarton vagy tégla?"
            >
              TOVÁBB OLVASOK
            </NuxtLink>
          </div>
        </article>

        <!-- 3. kártya -->
        <article class="blog__card">
          <div class="blog__card-image">
            <NuxtImg
              src="/img/test.png"
              alt="Személy lámpával szigetelés alatt"
            />
          </div>
          <div class="blog__card-content">
            <h3 class="blog__card-title">
              HŐSZIGETELÉS 2025-BEN – MIRE FIGYELJ, HA SPÓROLNI SZERETNÉL A
              FŰTÉSSZÁMLÁN?
            </h3>
            <p class="blog__card-text">
              Hasznos tippek és korszerű technológiák a hatékony
              hőszigeteléshez, hogy kevesebbet fizess a fűtésért és komfortosabb
              legyen az otthonod.
            </p>
            <NuxtLink
              to="#"
              class="blog__card-button"
              aria-label="Tovább olvasok: Hőszigetelés 2025-ben"
            >
              TOVÁBB OLVASOK
            </NuxtLink>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use 'sass:color';
.blog {
  background-color: #f5f5f5;
  padding: 18em 2em 28em 2em;
  margin-top: -17em;

  &__inner {
    max-width: 1200px;
    margin: 0 auto;
  }

  &__title {
    font-size: 2rem;
    font-weight: 700;
    color: #000000;
    margin-bottom: 1.5em;
  }

  &__cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;

    @media (max-width: 1024px) {
      grid-template-columns: repeat(2, 1fr);
    }

    @media (max-width: 768px) {
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
    }
  }

  &__card {
    background-color: #ffffff;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    box-shadow: 0px 10px 15px -3px rgba(0, 0, 0, 0.1),
      0px 4px 6px -2px rgba(0, 0, 0, 0.05);

    &-image {
      width: 100%;

      /* A NuxtImg komponens által létrehozott képstruktúra */
      > picture,
      > img,
      > div {
        display: block;
        width: 100%;
        height: auto;
        object-fit: cover;
      }
    }

    &-content {
      padding: 1.5rem;
      flex: 1 1 auto;
      display: flex;
      flex-direction: column;
    }

    &-title {
      font-size: 1.125rem;
      font-weight: 700;
      color: #000000;
      margin: 0 0 0.75rem 0;
      line-height: 1.3;
    }

    &-text {
      font-size: 1rem;
      line-height: 1.6;
      color: #333333;
      margin-bottom: 1.5rem;
      flex: 1 1 auto;
    }

    &-button {
      display: inline-block;
      background-color: #f5a623;
      color: #ffffff;
      text-transform: uppercase;
      font-weight: 700;
      font-size: 1rem;
      text-decoration: none;
      padding: 10px 24px;
      border-radius: 34px;
      align-self: flex-start;
      transition: background-color 0.2s ease;

      &:hover,
      &:focus {
        background-color: color.adjust(#f5a623, $lightness: -10%);
      }
    }
  }
  @media (max-width: 768px) {
    padding: 15em 2em 25em 2em;
  }
}
</style>
