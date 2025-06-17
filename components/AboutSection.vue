<template>
  <section class="about-us">
    <div class="about-us__inner">
      <!-- Left side: Text content -->
      <div class="about-us__content">
        <h2 class="about-us__title">RÓLUNK</h2>

        <p class="about-us__text">
          A SolDACH Kft. egy fiatal, lendületes építőipari vállalkozás, amelyet
          azzal a céllal hoztunk létre, hogy megbízható, átlátható és magas
          színvonalú szolgáltatást nyújtsunk partnereinknek. Saját
          alkalmazottainkkal dolgozunk – nem alvállalkozókkal –, így teljes
          kontrollt tudunk biztosítani a munkafolyamatok felett, és garantálni
          tudjuk a minőséget, valamint a pontos határidőket.
        </p>

        <p class="about-us__text">
          Többéves szakmai tapasztalattal a hátunk mögött olyan megoldásokat
          kínálunk, amelyekre ügyfeleink hosszú távon is számíthatnak. Főbb
          szolgáltatásaink közé tartozik a bontás, kőműves munkák, szárazépítés,
          hőszigetelés és a szerkezetépítés – minden projektünk során a
          precizitást és a megbízhatóságot tartjuk szem előtt.
        </p>

        <p class="about-us__text">
          Székhelyünk Budapesten, a XIII. kerületben található, de rugalmasan
          vállalunk munkákat szerte az országban is. Legyen szó kisebb
          lakásfelújításról vagy nagyobb kivitelezési projektről, a SolDACH
          csapata kész áll arra, hogy Önnel együtt valósítsa meg elképzeléseit.
        </p>

        <p class="about-us__text about-us__text--highlight">
          Keressen minket bizalommal, és csatlakozzon elégedett ügyfeleink
          köréhez!
        </p>

        <a
          href="mailto:info@soldach.hu"
          class="about-us__button"
          aria-label="Írjon e-mailt a SolDACH Kft.-nek"
        >
          ÍRJON E-MAILT
        </a>
      </div>

      <!-- Right side: Image -->
      <div class="about-us__image-wrapper">
        <NuxtImg
          src="/img/test.png"
          alt="A SolDACH csapata egy építkezésen"
          class="about-us__image"
        />
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use 'sass:color';
.about-us {
  background-color: #ffffff;
  padding: 5em 2em;

  &__inner {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
  }

  &__content {
    flex: 1 1 500px;
    padding-right: 2rem;

    @media (max-width: 768px) {
      padding-right: 0;
    }
  }

  &__title {
    font-size: 2rem;
    font-weight: 700;
    margin-bottom: 1.5rem;
    color: #000000;
  }

  &__text {
    font-size: 1rem;
    line-height: 1.6;
    margin-bottom: 1rem;
    color: #333333;

    &--highlight {
      font-weight: 600;
      color: #000000;
    }
  }

  &__button {
    display: inline-block;
    background-color: #f5a623;
    color: #ffffff;
    text-transform: uppercase;
    font-weight: 700;
    font-size: 1rem;
    text-decoration: none;
    padding: 10px 24px;
    border-radius: 34px;
    transition: background-color 0.2s ease;

    &:hover,
    &:focus {
      // A Sass 1.50+ esetén a darken() helyett:
      background-color: color.adjust(#f5a623, $lightness: -10%);
    }
  }

  &__image-wrapper {
    flex: 1 1 400px;
    max-width: 600px;
    margin-top: 1rem;

    @media (max-width: 768px) {
      margin-top: 2rem;
    }
  }

  &__image {
    display: block;
    width: 100%;
    height: auto;
  }

  @media (max-width: 768px) {
    padding: 3em 2em;
    &__inner {
      flex-direction: column;
      align-items: center;
    }

    &__image-wrapper {
      width: 100%;
      max-width: 100%;
      flex: unset;
    }
  }
}
</style>
