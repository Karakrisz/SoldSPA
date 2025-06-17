<template>
  <section class="works">
    <div class="works__inner">
      <!-- 1. blokk: bal oldalon kép, jobb oldalon narancs text‐box -->
      <div class="works__item works__item--image">
        <NuxtImg
          src="/img/works.webp"
          alt="Építési helyszín belső részlet"
          class="works__item-image"
        />
      </div>
      <div class="works__item works__item--text works__item--text--orange">
        <div class="works__item-text">
          <p>Mi nem csak beszélünk a minőségről – meg is mutatjuk.</p>
          <p>
            Minden projektünk során dokumentáljuk a munkafolyamatokat, hogy Ön
            is lássa, mennyire fontos számunkra a precizitás és a szakmaiság.
            Legyen szó falbontásról, vakolásról vagy hőszigetelésről, nálunk
            nincs rejtett munka – minden lépés átlátható.
          </p>
          <p>
            Nézzen bele a munkanapjainkba, és tapasztalja meg, milyen egy igazi,
            elkötelezett csapat, akik tényleg értenek ahhoz, amit csinálnak!
          </p>
        </div>
      </div>

      <!-- 2. blokk: bal oldalon fekete text‐box, jobb oldalon kép -->
      <div class="works__item works__item--text works__item--text--black">
        <div class="works__item-text">
          <p>Hiszünk abban, hogy a legjobb ajánlólevél a befejezett munkánk.</p>
          <p>
            Ezért is osztjuk meg rendszeresen az általunk végzett felújítások és
            építkezések részleteit – valós helyszíneken, valós ügyfelekkel.
            Minden videó egy-egy történet: problémából megoldás, elképzelésből
            valóság.
          </p>
          <p>
            Ha kíváncsi arra, hogyan lehet egy romos helyiségből modern és
            praktikus tér, itt a helye! Nézze meg, hogyan dolgozik a SolDACH
            csapata élesben.
          </p>
        </div>
      </div>
      <div class="works__item works__item--image">
        <NuxtImg
          src="/img/works2.webp"
          alt="Építési helyszín külső részlet"
          class="works__item-image"
        />
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use 'sass:color';
.works {
  background-color: #ffffff;
  padding: 5em 0;

  &__inner {
    max-width: 1000px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-auto-rows: auto;
    gap: 1.5rem;

    @media (max-width: 768px) {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }
  }

  &__item {
    &--image {
      // Itt nincs extra wrapper, a NuxtImg-nek adjuk a full-width stílust
      .works__item-image {
        display: block;
        width: 100%;
        height: auto;
        object-fit: cover;
      }
    }

    &--text {
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 1.5rem;

      &--orange {
        background-color: #f5a623;
        color: #ffffff;

        .works__item-text p {
          margin-bottom: 1rem;
        }
        .works__item-text p:last-child {
          margin-bottom: 0;
        }
      }

      &--black {
        background-color: #191919;
        color: #ffffff;

        .works__item-text p {
          margin-bottom: 1rem;
        }
        .works__item-text p:last-child {
          margin-bottom: 0;
        }
      }

      .works__item-text {
        max-width: 500px;
        font-size: 1rem;
        line-height: 1.6;
        @media (max-width: 768px) {
          padding: 1em;
        }
      }
    }
  }

  // Mobilra minden blokk full-width:
  @media (max-width: 768px) {
    &__item {
      &--image,
      &--text {
        width: 100%;
      }
    }
  }
}
</style>
