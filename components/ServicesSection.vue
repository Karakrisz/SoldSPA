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
            <NuxtImg
              class="services__content-image__img"
              src="/img/bontas.webp"
              alt="Bontási munkálatok példája"
            />
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
            <NuxtImg
              class="services__content-image__img"
              src="/img/komuves.webp"
              alt="Kőműves munkák példája"
            />
          </div>
          <div class="services__content-details">
            <h3 class="services__content-title">Kőműves munkák</h3>
            <p class="services__content-text">
              A kőműves munkák az építkezés alapját képezik – ezek a precíz,
              szakszerű tevékenységek határozzák meg az épület tartósságát és
              esztétikai értékét. Minden falazási, vakolási és burkolási munka
              során törekszünk a legmagasabb minőségre, legyen szó új építésről
              vagy felújításról.
            </p>
            <p class="services__content-text">
              Csapatunk minden kőműves munkát alaposan megtervez, figyelembe
              véve az építészeti igényeket és a helyi adottságokat. Fontos
              számunkra a precizitás, a tiszta munkavégzés, és hogy minden
              munkafázis után kifogástalan eredményt érjünk el.
            </p>
            <ul class="services__content-list">
              <li class="services__content-item">
                <strong>Falazási munkák</strong><br />
                Tégla, ytong és egyéb építőelemek szakszerű falazása, teherhordó
                és válaszfalak építése precíz kivitelezéssel.
              </li>
              <li class="services__content-item">
                <strong>Vakolási munkák</strong><br />
                Belső és külső vakolatok készítése, simítása, dekoratív
                vakolatok és különleges felületkezelések alkalmazása.
              </li>
              <li class="services__content-item">
                <strong>Csempézés és burkolás</strong><br />
                Fürdőszobák, konyhák és egyéb helyiségek csempézése,
                padlóburkolatok lerakása szakszerű ragasztással és fugázással.
              </li>
              <li class="services__content-item">
                <strong>Járda és térburkolás</strong><br />
                Kültéri járdák, teraszok és udvarok burkolása térkővel,
                természetes kővel vagy betonlapokkal.
              </li>
              <li class="services__content-item">
                <strong>Kémények és kandallók építése</strong><br />
                Kémények falazása, kandallók építése és felújítása, tűzálló
                anyagok szakszerű alkalmazásával.
              </li>
              <li class="services__content-item">
                <strong>Javítási és karbantartási munkák</strong><br />
                Meglévő falazatok javítása, vakolatok felújítása, repedések
                megszüntetése és egyéb karbantartási feladatok.
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
            <NuxtImg
              class="services__content-image__img"
              src="/img/komuves2.webp"
              alt="Száraz építés munkálatok"
            />
          </div>
          <div class="services__content-details">
            <h3 class="services__content-title">Száraz építés</h3>
            <p class="services__content-text">
              A száraz építés a modern építőipar egyik leghatékonyabb módszere –
              ez a technológia gyors, tiszta és környezetbarát megoldásokat
              kínál minden építkezési igényre. A száraz építési technikák
              alkalmazásával minimalizáljuk a szárítási időt és a nedvességgel
              járó problémákat, így rövidebb határidővel dolgozhatunk.
            </p>
            <p class="services__content-text">
              Csapatunk a száraz építés minden területén jártas, a legmodernebb
              anyagokat és technológiákat alkalmazva. Fontos számunkra a
              pontosság, a pormentes munkavégzés, és hogy minden projekt
              gazdaságos és tartós megoldást jelentsen ügyfeleink számára.
            </p>
            <ul class="services__content-list">
              <li class="services__content-item">
                <strong>Gipszkarton rendszerek</strong><br />
                Falak, álmennyezetek és térelválasztók építése gipszkarton
                lemezekkel, fém vázszerkezettel.
              </li>
              <li class="services__content-item">
                <strong>Gipszrost építés</strong><br />
                Speciális gipszrost lemezek felhasználásával készült
                konstrukciók, nagyobb terhelhetőséggel és stabilitással.
              </li>
              <li class="services__content-item">
                <strong>OSB és furnér alapú építés</strong><br />
                OSB lapok és furnér lemezek alkalmazása falakhoz, padlókhoz és
                tetőszerkezetekhez tartós megoldásokkal.
              </li>
              <li class="services__content-item">
                <strong>Szendvicspanel rendszerek</strong><br />
                Szigetelt szendvicspanelek beépítése gyors falépítéshez, kiváló
                hő- és hangszigetelő tulajdonságokkal.
              </li>
              <li class="services__content-item">
                <strong>Moduláris építés</strong><br />
                Előre gyártott elemek összeszerelése helyszínen, gyors és precíz
                építkezési megoldásokkal.
              </li>
              <li class="services__content-item">
                <strong>Laminált padlók és falburkolatok</strong><br />
                Száraz technológiával történő padló- és falburkolás, ragasztó
                nélküli click rendszerekkel és speciális rögzítésekkel.
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
  background-color: #f0f0f0;
  padding: 5em 2em;

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
    margin: 0 0 1em 0;
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
    background-color: #ffe3ba; // világos sárga
    color: #fff;
    padding: 0.5rem 1rem;
    border: none;
    border-radius: 999px;
    font-weight: 700;
    font-size: 1rem;
    cursor: pointer;
    transition: background-color 0.2s ease;
    text-transform: uppercase;

    &:hover,
    &:focus {
      background: #f4a32a;
    }

    &--active {
      border-radius: 34px;
      background: #f4a32a;
      color: #ffffff;
      padding: 10px 24px;
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
      height: 40.5em;
      overflow: hidden;
      object-fit: cover;
      @media (max-width: 768px) {
        height: 100%;
      }
    }
  }

  &__content-details {
    flex: 1 1 500px;
  }

  &__content-title {
    font-size: 1.5rem;
    font-weight: 600;
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
  @media (max-width: 768px) {
    padding: 3em 2em;
  }
}
</style>
