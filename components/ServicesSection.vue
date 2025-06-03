<script setup>
import { ref } from 'vue'
// Ha nincs automatikus importálás engedélyezve a NuxtImg-nek, akkor vedd elő a sor alább:
// import { NuxtImg } from '#components'

const serviceList = [
  { key: 'bontas', label: 'Bontás' },
  { key: 'komuves', label: 'Kőműves munkák' },
  { key: 'szarazEpites', label: 'Száraz építés' },
  // ide írd a további szolgáltatások kulcsait és címkéit, ha lesznek
]

const activeTab = ref('bontas')
</script>

<template>
  <section class="services">
    <div class="services__inner">
      <!-- Fejléc és tab-ok -->
      <div class="services__header">
        <h2 class="services__title">SZOLGÁLTATÁSOK</h2>
        <div class="services__tabs">
          <button
            v-for="(service, index) in serviceList"
            :key="service.key"
            :class="[
              'services__tab',
              { 'services__tab--active': activeTab === service.key },
            ]"
            @click="activeTab = service.key"
          >
            {{ service.label }}
          </button>
        </div>
      </div>

      <!-- Tartalom -->
      <div class="services__content-wrapper">
        <!-- Bontás (aktív tab) -->
        <div
          v-if="activeTab === 'bontas'"
          class="services__content services__content--bontas"
        >
          <div class="services__content-image">
            <NuxtImg src="/img/test.png" alt="Bontási munkálatok példája" />
          </div>
          <div class="services__content-details">
            <h3 class="services__content-title">Bontás</h3>
            <p class="services__content-text">
              A bontás nem csupán az épületek lebontásáról szól – ez az egyik
              legfontosabb előkészítő fázis minden felújítás vagy építkezés
              előtt. A szakszerűen végzett bontási munkák megalapozzák a további
              kivitelezés gördülékenységét, legyen szó egy kisebb lakásról vagy
              nagyobb ipari ingatlanról.
            </p>
            <p class="services__content-text">
              Csapatunk minden bontási munkát precízen megtervez, a helyszín
              adottságait figyelembe véve. Fontos számunkra a biztonság, a
              rendezettség, és hogy a bontás után tiszta, jól előkészített
              munkaterületet hagyjunk magunk után.
            </p>
            <ul class="services__content-list">
              <li class="services__content-item">
                <strong>Válaszfalak bontása</strong><br />
                Gipszkarton, ytong vagy téglafalak gyors és pormentes
                eltávolítása, különösen belső térátalakítások során.
              </li>
              <li class="services__content-item">
                <strong>Csempék és burkolatok eltávolítása</strong><br />
                Régi padló- és falburkolatok precíz bontása, hogy az új burkolás
                tökéletesen kivitelezhető legyen.
              </li>
              <li class="services__content-item">
                <strong>Aljzatbontás</strong><br />
                Régi beton vagy esztrich aljzatok bontása gépi vagy kézi
                módszerrel, igény szerint.
              </li>
              <li class="services__content-item">
                <strong>Nyílászárók kibontása</strong><br />
                Ablakok és ajtók bontása úgy, hogy a környezet sértetlen
                maradjon, előkészítve az új nyílászárók beépítését.
              </li>
              <li class="services__content-item">
                <strong>Teljes helyiségek bontása</strong><br />
                Konyhák, fürdőszobák vagy egyéb helyiségek komplett elbontása a
                gépeszet, burkolatok és szerkezetek eltávolításával együtt.
              </li>
              <li class="services__content-item">
                <strong>Törmelék elszállítása</strong><br />
                Minden bontás után gondoskodunk a keletkezett sitt szakszerű
                összegyűjtéséről és elszállításáról is, hogy Önnek ezzel se
                kelljen foglalkoznia.
              </li>
            </ul>
          </div>
        </div>

        <!-- Kőműves munkák (példa) -->
        <div
          v-if="activeTab === 'komuves'"
          class="services__content services__content--komuves"
        >
          <div class="services__content-image">
            <NuxtImg src="/img/test.png" alt="Kőműves munkák példája" />
          </div>
          <div class="services__content-details">
            <h3 class="services__content-title">Kőműves munkák</h3>
            <p class="services__content-text">
              <!-- Ide jöhet a „Kőműves munkák” szövege -->
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla
              facilisi.
            </p>
            <ul class="services__content-list">
              <li class="services__content-item">
                <strong>Példa tétel 1</strong><br />
                Leírás a kőműves munkákhoz.
              </li>
              <li class="services__content-item">
                <strong>Példa tétel 2</strong><br />
                Egyéb információ a kőműves munkákról.
              </li>
            </ul>
          </div>
        </div>

        <!-- Száraz építés (példa) -->
        <div
          v-if="activeTab === 'szarazEpites'"
          class="services__content services__content--szarazEpites"
        >
          <div class="services__content-image">
            <NuxtImg src="/img/test.png" alt="Száraz építés munkálatok" />
          </div>
          <div class="services__content-details">
            <h3 class="services__content-title">Száraz építés</h3>
            <p class="services__content-text">
              <!-- Ide jöhet a „Száraz építés” szövege -->
              Vivamus luctus urna sed urna ultricies ac tempor dui sagittis.
            </p>
            <ul class="services__content-list">
              <li class="services__content-item">
                <strong>Példa tétel A</strong><br />
                Részletek a száraz építésről.
              </li>
              <li class="services__content-item">
                <strong>Példa tétel B</strong><br />
                További információ a száraz építésről.
              </li>
            </ul>
          </div>
        </div>

        <!-- További szolgáltatásokhoz hasonlóan... -->
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use 'sass:color';
.services {
  background-color: #f5f5f5;
  padding: 2rem 1rem;

  &__inner {
    max-width: 1200px;
    margin: 0 auto;
  }

  &__header {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 2rem;

    @media (max-width: 768px) {
      flex-direction: column;
      align-items: flex-start;
    }
  }

  &__title {
    font-size: 2rem;
    font-weight: 700;
    color: #000000;
    margin: 0;
  }

  &__tabs {
    display: flex;
    gap: 1rem;

    @media (max-width: 768px) {
      margin-top: 1rem;
      width: 100%;
      flex-wrap: wrap;
    }
  }

  &__tab {
    background-color: #ffe5b5; // világos sárga
    color: #000000;
    padding: 0.5rem 1rem;
    border: none;
    border-radius: 999px;
    font-weight: 600;
    font-size: 0.9375rem;
    cursor: pointer;
    transition: background-color 0.2s ease;

    &:hover,
    &:focus {
      background-color: color.adjust(#ffe5b5, $lightness: -8%);
    }

    &--active {
      background-color: #f5a623; // élénk sárga/orange, kiemelt
      color: #ffffff;
    }
  }

  &__content-wrapper {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }

  &__content {
    display: flex;
    align-items: flex-start;
    gap: 2rem;

    @media (max-width: 768px) {
      flex-direction: column;
      gap: 1rem;
    }
  }

  &__content-image {
    flex: 1 1 400px;

    & > picture,
    & > img,
    & > div {
      /* A <NuxtImg> belső struktúrája miatt célszerű így célozni */
      width: 100%;
      height: auto;
      border-radius: 4px;
      overflow: hidden;
    }
  }

  &__content-details {
    flex: 1 1 500px;
  }

  &__content-title {
    font-size: 1.5rem;
    font-weight: 700;
    margin-bottom: 1rem;
    color: #000000;
  }

  &__content-text {
    font-size: 1rem;
    line-height: 1.6;
    color: #333333;
    margin-bottom: 1rem;
  }

  &__content-list {
    list-style: disc;
    margin-left: 1.25rem;
    margin-bottom: 1rem;

    .services__content-item {
      margin-bottom: 0.75rem;
      font-size: 0.9375rem;
      line-height: 1.5;
      color: #333333;

      strong {
        font-weight: 600;
      }
    }
  }
}
</style>
